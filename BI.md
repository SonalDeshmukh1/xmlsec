# Building XMLSec

Below versions of XMLSec are available in respective distributions:

*    RHEL (7.8, 7.9) have `1.2.20`
*    RHEL (8.4, 8.6, 8.7) have `1.2.25`
*    RHEL (9.0, 9.1) have `1.2.29`
*    SLES (12 SP5, 15 SP4) have `1.2.28`
*    Ubuntu 18.04 has `1.2.25`
*    Ubuntu 20.04 has `1.2.28`
*    Ubuntu 22.04 has `1.2.33`
*    Ubuntu 22.10 has `1.2.34`
*    ubuntu 23.04 has `1.2.37`

The instructions provided below specify the steps to build [XMLSec](https://www.aleksey.com/xmlsec/) 1.2.37 on Linux on IBM Z for following distributions:

*    RHEL (7.8, 7.9, 8.4, 8.6, 8.7, 9.0, 9.1)
*    SLES (12 SP5, 15 SP4)
*    Ubuntu (18.04, 20.04, 22.04, 22.10, 23.04)

_**General Notes:**_

 * _When following the steps below please use a standard permission user unless otherwise specified._
 * _A directory `/<source_root>/` will be referred to in these instructions, this is a temporary writable directory anywhere you'd like to place it_

## Step 1: Build and Install XMLSec

#### 1) Install dependencies

*   RHEL (7.8, 7.9)
    ```shell
    sudo yum install -y git make libtool libxslt-devel libtool-ltdl-devel diffutils devtoolset-7 texinfo gettext transfig
    ```

*   RHEL (8.4, 8.6, 8.7)
    ```shell
    sudo yum install -y git make libtool libxslt-devel libtool-ltdl-devel diffutils 
    ```
    
*   RHEL (9.0, 9.1)
    ```shell
    sudo yum install -y git make libtool libxslt-devel libtool-ltdl-devel diffutils libgcrypt-devel
    ```
    
*   SLES 12 SP5
    ```shell
    sudo zypper install -y git-core make libtool libxslt-devel libopenssl-devel gawk gcc7 gcc7-c++ texinfo gettext transfig
    sudo ln -sf /usr/bin/gcc-7 /usr/bin/gcc
    sudo ln -sf /usr/bin/g++-7 /usr/bin/g++
    sudo ln -sf /usr/bin/gcc /usr/bin/cc
    ```

*   SLES (15 SP4)
    ```shell
    sudo zypper install -y git-core gcc make libtool libxslt-devel libopenssl-devel gawk
    ```

*  Ubuntu (18.04, 20.04, 22.04, 22.10, 23.04)
   ```shell
   sudo apt-get update
   sudo apt-get install -y git make libtool libxslt1-dev autoconf libssl-dev libtool-bin pkg-config
    ```

#### 2) Enable Software Collections: (Only for RHEL 7.x)

   Xmlsec requires GCC 7. It is available on RHEL 7.x via the 'Software Collections' packaging system. You can find out more about Software Collections
   here: https://www.softwarecollections.org/en/.
   
   Following command will enable GCC 7. The changes are not persistent and these commands will need to be re-run every time a new terminal session is started.
   
   ```
   scl enable devtoolset-7 bash
   ```
#### 3) Build and install automake, libgpg-error and libgcrypt from source(Only for RHEL 7.x)

   ```shell
      cd $SOURCE_ROOT
      git clone https://github.com/autotools-mirror/automake.git
      cd automake
      git checkout v1.16.5
      ./bootstrap
      ./configure
      make
      sudo make install
      automake --version

      cd $SOURCE_ROOT
      git clone https://github.com/gpg/libgpg-error.git
      cd libgpg-error
      git checkout  libgpg-error-1.25
      ./autogen.sh
      ./configure --enable-maintainer-mode && make
      sudo make install
      gpg-error-config --version

      cd $SOURCE_ROOT
      git clone https://github.com/gpg/libgcrypt.git
      cd libgcrypt
      git checkout libgcrypt-1.8.5
      ./autogen.sh
      ./configure --enable-maintainer-mode && make
      sudo make install
      libgcrypt-config --version
   ```
#### 4) Build and install automake and libgcrypt from source(Only for 12 SP5)

   ```shell
      cd $SOURCE_ROOT
      git clone https://github.com/autotools-mirror/automake.git
      cd automake
      git checkout v1.16.4
      ./bootstrap
      ./configure
      make
      sudo make install
      automake --version
      
      cd $SOURCE_ROOT
      git clone https://github.com/gpg/libgcrypt.git
      cd libgcrypt
      git checkout libgcrypt-1.8.5
      ./autogen.sh
      ./configure --enable-maintainer-mode && make
      sudo make install
      libgcrypt-config --version
   ```

#### 5) Build and install OpenSSL from source(Only for Ubuntu 22.04)

   Openssl 3.0 is available in repository for ubuntu 22.04 which is not supported by libtools
   ```shell
     cd $SOURCE_ROOT
     wget https://www.openssl.org/source/openssl-1.1.1h.tar.gz
     tar -xzvf openssl-1.1.1h.tar.gz
     cd openssl-1.1.1h
     ./config --prefix=/usr/local --openssldir=/usr/local
     make
     sudo make install

     export LDFLAGS="-L/usr/local/lib/ -L/usr/local/lib64/"
     export LD_LIBRARY_PATH=/usr/local/lib/:/usr/local/lib64/:/usr/lib/:/usr/lib64/${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
     export CPPFLAGS="-I/usr/local/include/ -I/usr/local/include/openssl"
   ```

#### 6) Get the source code
   ```shell
     export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
     cd $SOURCE_ROOT
     git clone https://github.com/lsh123/xmlsec.git
     cd xmlsec
     git checkout xmlsec_1_3_0
   ```
#### 7) Setting the environment variable ACLOCAL_PATH to /usr/share/aclocal.(Only for RHEL 7.x and 12 SP5) 
   ```
     export ACLOCAL_PATH=/usr/share/aclocal
   ``` 
#### 8) Generate and then run the configuration
   ```
     ./autogen.sh
   ```
   
#### 9) Build and (_optionally_) test
   ```shell
     make
     make check
   ```
   
#### 10) Install XMLSec and verify the installation
   ```shell
     sudo make install
     xmlsec1 --version
   ```
   
### References:
- https://www.aleksey.com/xmlsec/ 
- https://github.com/lsh123/xmlsec
