**Package name: XMLSec v1.3.0**

**Currency Checklist:**

Tasks | Details 
-- | --
Check the Latest stable version | <b>v1.3.0 https://github.com/lsh123/xmlsec/releases </b>
Provide list of supported distros mentioned by community. Share link for reference.<br><br>Add support for following   Distros:<br>  RHEL 7.8, RHEL 7.9, RHEL 8.6, RHEL 8.7, RHEL 9.0, RHEL 9.1, SLES12 SP5, SLES15 SP4, Ubuntu 20.04(LTS), Ubuntu 22.04(LTS),  Ubuntu 22.10,  Ubuntu 23.04<br> Supported distro list should match   what community claims. If any community claimed distro is not worked on, give   appropriate reasons.<br><br> (Note: Format community claim statement in italics if applicable) <br>Note: Updates on below distros:<br>RHEL 8.4 - EOL: 2023/05/31<br>Ubuntu 18.04 - EOL: 2023/06/30<br>Ubuntu 22.10- EOL: 2023/07/31<br>Ubuntu 23.04- GA: 2023/04/20 | <b>Supports debian/linux distros<br><br>https://www.aleksey.com/xmlsec/download.html<br><br><ul><li> Added support to RHEL (7.8, 7.9, 8.4, 8.6, 8.7, 9.0, 9.1)</li><br><li> Ubuntu (20.04, 22.04, 22.10, 23.04)</li><br><li>SLES (12 SP5, 15 SP4)</li></ul></b>
Provide list of supported runtimes mentioned by community. Share link for reference. <br> (Note: Format community claim statement in italics if applicable) <br> Provide list of verified runtimes as mentioned by community. <br>Eg: Go/Java/Gcc etc <br>(Refer Java guidelines below, for more info)  <br>If any community claimed runtimes are not worked on, give   appropriate reasons.  | 
Package   available in distribution? If yes, list distos along with versions available |  <b>Yes<br><br><ul><li>RHEL (7.8, 7.9) have 1.2.20</li><li>RHEL (8.4, 8.6, 8.7) have 1.2.25</li><li>RHEL (9.0, 9.1) have 1.2.29</li><li>SLES (12 SP5, 15 SP4) have 1.2.28</li><li>Ubuntu 20.04 has 1.2.28</li><li>Ubuntu 22.04 has 1.2.33</li><li>Ubuntu 22.10 has 1.2.34</li><li>ubuntu 23.04 has 1.2.37</li></ul></b>
Languages used – List all the languages used in Source. <br><br>Update the Package Status excel sheet <br>https://ibm.ent.box.com/file/910316005555 |   <b><ul><li>C 93.9 %</li> <li>Shell 3.4%</li> <li>M4 1.9%</li> <li>Javascript 0.4%</li> <li>Makefile 0.3%</li> <li>Perl 0.1%</li></ul></b>
CI/CD info: <br> Community using any CI/CD tool? Yes/No<br>If yes, answer questions in the next column for each CI/CD tools <br> | <b> Yes , Github Actions https://github.com/lsh123/xmlsec/actions</b><br>1. Is Z part of the CI? <b>No</b><br>&nbsp;&nbsp;&nbsp;&nbsp;If yes, <br>&nbsp;&nbsp;&nbsp;&nbsp;1.1. working properly & build succ? <b>&nbsp;&nbsp;NA</b><br> 2.  List archs being built<br><b>Win2002-x86-64, macOS and amd64</b><br>3. Is the package cross compiled?<b>&nbsp;&nbsp;No</b> <br>4. Is this CI responsible for releasing any build artifact (e.g., binary/docker image/operator)  <b>&nbsp;&nbsp;No</b><br>5. Is this CI for build only? <b>Yes</b><br>6. Is testing part of the CI (What kind of testing. E.g. unit test, integration test) <b>No</b><br>7.   Is CI part of PR checks or PR merge commits? <b>Yes</b><br> 8. If Z is not already part of CI, then look for chances to add Z support, share details like how to enable, etc, discussion is needed before we decide what to do. <b>XMLSec GA enablement work was stopped by the Z-team because the following issues-https://github.ibm.com/loz/opensource-porting-s390x/issues/3237#issuecomment-29709786</b>
Binary info:<br>Are Binaries (in any format) available? If yes, provide details:  |  1.	List all architectures (including no-arch/no-mention) for which binaries are available and share link to download.<br><b>win32 https://github.com/lsh123/xmlsec/releases</b><br>2. Provide details on how it is built e.g. cross vs native <b> Native</b><br>3.	Tools being used to create binary <b> mingw</b><br>4.	CI responsible for releasing the binary<b>NA</b><br>5.	Is emulator used?<b>NA</b><br>6.	Verify/test binaries and share results. <br>7.	If Binary is not available for Z then look for chances to add Z support, share details like how to enable, etc, discussion is needed before we decide what to do.<b>The binaries are being built by the nmake-cmd and is used for building only win32 no info found about supporting binaries on other platforms including linux and macOS,link- https://github.com/lsh123/xmlsec/tree/224da414f609289fa6514f4f7b70244fefc098ff/win32</b>
Docker Image info:<br> Dockerfile/images available externally for Intel?If Yes, provide details: | <b>Intel dockerfile not found and ibmcom/xmlsec-s390x has docker image for 1.2.27(https://hub.docker.com/r/ibmcom/xmlsec-s390x)</b><br>  1.	Intel Dockerfile link:  <br>2. s390x Dockerfile link (Maintained by us / Community):<br>&nbsp;&nbsp;&nbsp;2.1 If maintained by us,      Dockerfile should be provided and should as close to Intel as possible. Provide difference with Intel if any and why<br>&nbsp;&nbsp;&nbsp;2.2	If maintained by us,      mention Intel and s390x docker image sizes. Provide difference with Intel if any and why <br>3.	Docker image link (for s390x and other platforms like Intel, amd, ppc64 etc): <br>(Search as many keywords as u can think of – e.g.  dockerhub, google, gcloud , Rhel registry etc)<br>4.	Mention the CI responsible for building   and publishing docker image.<br>5.	Is emulator used?<br>6.	Mention tools used to build the image.<br>7.	If docker image is not available for Z then look for chances to add Z support, share details like how to enable, etc, discussion is needed before we decide what to do.
Operator info:<br> Are Operators available?   If yes, provide details:| <b>No</b><br>1. Which arch and where to find it (link should be provided). <b>&nbsp;&nbsp;NA</b> <br>2.   Generated from their CI/CD? <b>&nbsp;&nbsp;NA</b>
PR info:<br> Are there any code changes needed for this release?If Yes, If yes, list them all in the next column and answer question for each. | 1.	Should the code changes be PRed? If yes provide PR link. If Not PRed, provide reasons on why not.<b>&nbsp;&nbsp;No code changes</b> <br> 2.	Check if there are existing open PR’s and if it's still valid for this release <b>&nbsp;&nbsp;NA</b>
Issues info:| <br>1. Any issue created with community (GitHub, JIRA, Bugzilla etc)?If Yes, provide issue link.<b>&nbsp;&nbsp;No issues created</b><br>2.	Check if there are existing open issues and if it's still valid for this release. For any outstanding issue provide latest updates and issue table should be updated accordingly. <b>&nbsp;&nbsp;There are no issues or PR</b>
Internal Deliverables: | 1.	Created Test reports (Table format)?Use test result template<b>&nbsp;&nbsp;NA</b><br>2.	Is Zenhub issue updated with all UpToDate info including informal community communications<b>&nbsp;&nbsp;Yes</b><br>3.	List down detailed Steps followed to verify the package. Give reference link as well. Also Attach a proof of verification on the ZenHub issue<br><b>Followed the official document<br>(https://github.com/lsh123/xmlsec/blob/master/README.md) to build and verify the xmlsec 1.3.0.The logs are attached below</b>
External Deliverables: | 1.	Build Instructions <br>&nbsp;&nbsp;&nbsp;1.1	Is BI updated?<b>Yes</b><br>&nbsp;&nbsp;&nbsp;1.2	List all the changes done with respect to published version<br><b><ul><li>Added transfig, gettext and texinfo in the Install dependencies section of 7.x and 12 SP5</li><li>Added the steps for installing and building the automake, libgpg-error and libgcrypt from source for the 7.x and 12 SP5 distros</li><li>Added the command to set  the environment variable ACLOCAL_PATH</li><li>Changed the version of xmlsec to 1.3.0</li></ul></b>2.	Scripts <br>&nbsp;&nbsp;&nbsp;2.1	Is Script updated?<b>Not maintained</b><br>&nbsp;&nbsp;&nbsp;2.2	List all the changes done with respect to published version<b>NA</b><br>3.	Dockerfile  <br>&nbsp;&nbsp;&nbsp;3.1	Is Dockerfile updated?<b>There is no dockerfile</b><br>&nbsp;&nbsp;&nbsp;3.2	List all the changes done with respect to published version<b>NA</b> 
External table changes required? Add details about external table changes required (If any) (Check links, distro etc.) | <b>No</b>
  Actual efforts (In   hours) | <b>40 hours</b> 
  Calendar   Time (actual Start and End Date in yyyy/mm/dd) | <b>2023/04/14 - 2023/05/10</b>

* Java Variants on Z: 
  * **Java 8 (LTS)**: OpenJDK8, IBM Semeru Runtime Version 8.
  * **Java 11 (LTS)**: OpenJDK11, Eclipse Adoptium Temurin Runtime Version 11, [IBM Semeru Runtime Version 11 -> Not recommended for all packages. Discuss with the lead before trying out this variant].
  * **Java 17 (LTS)**: OpenJDK17, Eclipse Adoptium Temurin Runtime Version 17, [IBM Semeru Runtime Version 17 -> Not recommended for all packages. Discuss with the lead before trying out this variant]. 
 
**Guidelines:** 
* All Java versions mentioned by community should be tested
* If community does not mention any specific version of Java then use Java 11. Use Java 8 if Java 11 does not work.