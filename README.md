# nessus-vulnerablity-management
<h1>Description</h1>
This repo covers vulnerability scanning & remediation, vital steps in Vulnerability Management Lifecycle. We'll use Nessus Essentials to scan local VMs on VMWare, run credentialed scans, remediate some vulnerabilities, & verify with a rescan. Valuable experience for vulnerability management roles!
<br />


<h2>Languages and Utilities Used</h2>

- <b>Nessus essentials</b> 
- <b>Windows iso</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Install the VMWare pro <br/>
<img src="https://i.imgur.com/1Zm6kyw.png" height="80%" width="80%" alt="installation steps"/>
  <br />
  <br />
  Installing VMware Pro version is essential as it offers advanced options not available in the regular VMware. The Pro version enables smooth installation of Windows OS in the virtual machine (VM). This setup is necessary for my GitHub repository, where I'll be documenting projects and configurations involving VM environments.
<br />
<br />
Download Windows 10 ISO <br/>
<img src="https://i.imgur.com/lKVU27g.jpg" height="80%" width="80%" alt="installation steps"/>
<br />
<br />
In this project, I will download and install the Windows 10 ISO file to set up a target machine for Nessus vulnerability scanning. The installation of Windows 10 will be crucial as it will serve as the environment for conducting security scans using Nessus. By creating a dedicated target machine, I aim to perform thorough vulnerability assessments and document the process in my GitHub repository to enhance my cybersecurity skills and knowledge.
<br />
<br />
Network Adapter settings <br/>  
<img src="https://i.imgur.com/KMVtMRr.png" height="80%" width="80%" alt="installation steps"/>
<br />
<br />
Firmware type changing <br/>  
<img src="https://i.imgur.com/x1dNoWz.png" height="80%" width="80%" alt="installation steps"/>
<br />
<br />
In this guide, we will demonstrate how to install Windows ISO on VMware and optimize the setup for better performance. During the installation process, we will change the network adapter settings to 'Bridged' mode to ensure seamless connectivity with the host network. Additionally, we'll make necessary adjustments in the 'Options/Advanced/Firmware' settings by switching from UEFI to BIOS. These optimizations aim to create an efficient virtual machine environment for Windows.
<br />
<br />
  Nessus Instalation<br/>
<img src="https://i.imgur.com/SyD468V.png" height="80%" width="80%" alt="installation steps"/>
Tenable Nessus is a popular vulnerability scanning tool used to assess and identify security risks in networks, systems, and applications. It provides in-depth vulnerability scanning and assessment capabilities, enabling security professionals to proactively identify and remediate potential weaknesses in their IT infrastructure. The tool is widely used by organizations to enhance their security posture and protect against potential cyber threats.
<br />
<br />
  
Learn how to download and install Nessus Essentials by following this link: [https://bit.ly/nessus-essentials]. Nessus Essentials is a powerful vulnerability scanning tool that helps identify security weaknesses in systems and networks. By using this software, you can conduct credentialed scans and discover potential vulnerabilities in your environment.
<br />
<br />
  
</p>

<h2>Demonsteration</h2>

<h3>Ensure connectivity with VM</h3>
<p align="center">
  Ping Test<br/>
<img src="https://i.imgur.com/pYwf6Ne.png" height="80%" width="80%" alt="installation steps"/>
<br />
<br />
  In this guide, we will cover the essential step of ensuring connectivity with a Virtual Machine (VM). To achieve this, we'll ping the IP address of the VM's Windows OS by using the 'ipconfig' command in the Command Prompt. The ping will be initiated from the host OS (Windows) where Nessus is installed. If the ping returns a 'timed out' response, we'll take the necessary action of disabling all profiles in Windows Defender, effectively turning off Windows Defender. By implementing this procedure, we ensure a stable connection between the host and VM, enabling effective vulnerability scanning using Nessus. The documented steps will be added to my GitHub repository, facilitating others in enhancing their VM connectivity and vulnerability management practices.
<br />
<br />
  Create a new scan in Nessus<br/>
<img src="https://i.imgur.com/4f4peqF.png" height="80%" width="80%" alt="demonsteration steps"/>
<br />
<br />
 The process of creating a new scan in Nessus for effective vulnerability assessment. To begin, click on 'New Scan' and select 'Basic Network Scan' as the scan type. Next, provide a descriptive name for the targeted host. To specify the VM's OS, enter the corresponding IP address. Once all the required information is added, click on 'Save' to initiate the scan. This step-by-step guide will assist users in setting up scans efficiently and leveraging Nessus's capabilities for comprehensive vulnerability detection.
<br />
<br /> 
  </p>
<h2> now click on ▶️ this button </h2><br/>
<img src="https://i.imgur.com/Ff2sDys.png" height="80%" width="80%" alt="demonsteration steps"/>
<br />
<br />

  First Scan Result<br/>
<img src="https://i.imgur.com/fg7W2OG.png" height="80%" width="80%" alt="demonsteration steps"/>
<br />
<br />
In this section, we will inspect the results of the initial scan conducted without using any credentials. As expected, the first scan may not yield extensive results, but it serves as a crucial baseline for vulnerability assessment. Notably, the scan highlights 'SMB' as a medium vulnerability. Further exploration of this finding will be essential in subsequent scans with credentials. By documenting this process, we aim to showcase the importance of conducting multiple scans and leveraging credentials to obtain more comprehensive vulnerability insights.
<br />
<br />

</p>
<h2> Configuring VM for credentialed scans </h2><br/>
<p>
In this comprehensive guide, we will walk you through the process of configuring a Virtual Machine (VM) to enable credentialed scans, which are essential for conducting more thorough vulnerability assessments. Follow these steps to ensure a smooth setup:

1) Open 'services.msc' and enable the 'Remote Registry' service, setting it to automatic and starting it. This step allows Nessus to access the VM's registry remotely, facilitating detailed vulnerability checks. <br /> <br />
<img src="https://i.imgur.com/v95Kwbf.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />
2) Navigate to 'Advanced Sharing Settings' and turn on 'Network Discovery.' This setting allows Nessus to identify other devices on the network, enhancing the scan's scope and accuracy. <br /> <br />
<img src="https://i.imgur.com/0RuY7i5.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />
3) Access the 'User Access Control (UAC) Settings' and either set it to 'Never Notify' or disable it. By doing this, Nessus can seamlessly access and assess the VM's settings without encountering UAC prompts. <br /> <br />
<img src="https://i.imgur.com/ONmLuBO.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />
4) In the 'Registry Editor,' create a new DWORD (32-bit value) named 'LocalAccountTokenFilterPolicy' under 
LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System.' Set the value to 1. This key allows the remote account used by Nessus to connect effectively and disable user account control during scans. <br /> <br />
<img src="https://i.imgur.com/X00NqQl.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />
By completing these configurations, you will enable Nessus to perform credentialed scans effectively, enhancing the depth and accuracy of vulnerability detection. We are sharing this detailed guide on GitHub to empower others in optimizing their VM setup for vulnerability management and fostering better cybersecurity practices.
<br/> <br/>

</p>
<h2> Adding Credentials </h2><br/>
<p>

  In this step, we will add the necessary credentials to the saved IP network in Nessus. By providing the appropriate username and password, we enable Nessus to conduct credentialed scans on the target machines. <br/> <br/>
<img src="https://i.imgur.com/AqBSg4c.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br /> 
By documenting the process of adding credentials to the saved IP network in Nessus, we aim to assist others in conducting comprehensive vulnerability assessments. Properly configuring and utilizing Nessus with credentials enhances its capabilities and contributes to effective vulnerability management practices.  <br /> <br />

</p>
<h2>credential scan </h2><br/>
<h3> now click on ▶️ this button </h3><br/>
<p> 
<b>result of first credential scan</b><br/>
<img src="https://i.imgur.com/hynzgoZ.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />
  In this phase of the project, we conducted the first scan with credentials, which significantly enhanced the depth and accuracy of vulnerability assessment. The scan results revealed the following critical, high, and medium vulnerabilities:

1) Critical Vulnerabilities:

- Security Updates for Microsoft .NET Framework (June 2023)
- Microsoft Internet Explorer Unsupported Version Detection
- KB5028166: Windows 10 Version 20H2 / Windows 10 Version 21H2 / Windows 10 Version 2
- [Other high vulnerabilities]

2) High Vulnerabilities:

- Security Updates for Microsoft .NET Framework (June 2023)
- Microsoft Windows VP9 Video Extensions Library RCE (June 2021)
- [Other high vulnerabilities]

3) Medium Vulnerabilities:

- SMB Signing not required
- Microsoft Paint 3D Multiple Vulnerabilities (June 2021)
- [Other medium vulnerabilities]

In addition to these critical, high, and medium vulnerabilities, there were other findings categorized as low and informational, which may not be as critical but still warrant attention.

The scan results showcase the importance of conducting credentialed scans, as they provide deeper insights into the system's security posture. By documenting these findings, we aim to emphasize the significance of utilizing credentials to uncover critical vulnerabilities that might otherwise remain undetected.  <br /> <br />
<h3> Installing a deprecated Firefox on our VM </h3><br/>

<img src="https://i.imgur.com/DKZuxMo.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />

we will walk you through the process of installing a deprecated version of Firefox on our Virtual Machine (VM). A deprecated version of Firefox refers to an older version that is no longer supported or maintained by Mozilla, the developer of Firefox browser. In this case, we will install an older version of Firefox using the link: [https://bit.ly/deprecated-firefox].

Now, you might wonder why we are installing a deprecated version. There are a couple of reasons for doing so:

Compatibility Testing: As security professionals, it's essential to assess the security of systems and applications across different versions. By installing a deprecated Firefox version, we can simulate an environment that might still be using older browser versions. This allows us to identify potential security risks and vulnerabilities that might be specific to deprecated software.

Legacy Software Evaluation: Some organizations or users may still be using older software due to compatibility issues or other reasons. By exploring the deprecated version of Firefox, we can better understand potential security implications for users who are using outdated software. <br /> <br />
</p>
<h3> now click on ▶️ this button </h3><br/>

<h2>Inspect scan results after installing deprecated firefox </h2><br/>
<p>
  <img src="https://i.imgur.com/qGpdIOT.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />
  In this phase of the project, we inspected the scan results after installing the deprecated version of Firefox on the target IP. The scan provided the following vulnerabilities: <br/> <br/>

1) Critical Vulnerabilities:

- Firefox < 22.0 Multiple Vulnerabilities
- Firefox < 18.0 Multiple Vulnerabilities
- Mozilla Firefox < 67.0.4
- [Other critical vulnerabilities related to deprecated Firefox]
  
2) High Vulnerabilities:

- Security Updates for Microsoft .NET Framework (June 2023)
- Microsoft Windows HEIF Image Extensions RCE (March 2022)
- [Other high vulnerabilities]

3) Medium Vulnerabilities:

- SMB Signing not required
- Microsoft Paint 3D Multiple Vulnerabilities (June 2021)
- [Other medium vulnerabilities]<br/> <br/>

The critical vulnerabilities in this scan are specifically related to the deprecated version of Firefox we installed. This finding highlights the potential security risks associated with using older and unsupported software, such as the deprecated Firefox version.

By documenting these results, we aim to emphasize the importance of keeping software up-to-date to minimize potential security vulnerabilities. It also underscores the significance of conducting vulnerability assessments on various software versions to identify specific risks and improve overall security practices. <br/> <br/>

<h3> Remediating some vulnerabilities </h3><br/>
 <br/> <br/>
 n this step, we will focus on remediating some of the vulnerabilities we discovered, especially those related to the deprecated version of Firefox. To accomplish this, we will follow these important actions:

1) Uninstall Deprecated Firefox: The first remediation action is to uninstall the deprecated version of Firefox from the system. By removing the unsupported software, we eliminate the associated vulnerabilities and reduce potential security risks.

2) System Update: After uninstalling Firefox, we will proceed with updating the system to the latest patches and updates. Ensuring the system is up to date helps address security vulnerabilities and protects against known exploits.

The process will involve updating all relevant software and applying necessary security patches until the system status reflects "You're up to date." Once we complete these steps, the system will be in a more secure state, ready for the next vulnerability scan.<br/> <br/>

</p>
<h2>Inspect scan results after remediating some vulnerabilities </h2><br/>
<p>
  <b>last scan result</b><br/> <br/>
 <img src="https://i.imgur.com/DCH6Xin.png" height="80%" width="80%" alt="demonsteration steps"/> <br /> <br />
  In this phase of the project, we inspected the scan results after remediating some of the vulnerabilities that were previously detected. The updated scan now shows the following vulnerabilities:

1) Critical Vulnerability:

- Microsoft Internet Explorer Unsupported Version Detection

2) High Vulnerabilities:

- Microsoft Windows HEIF Image Extensions RCE (March 2022)
- WinVerifyTrust Signature Validation CVE-2013-3900 Mitigation (EnableCertPaddingCheck)
- [Other high vulnerabilities]

3) Medium Vulnerabilities:

- IP Forwarding Enabled
- Microsoft Paint 3D Multiple Vulnerabilities (June 2021)
- [Other medium vulnerabilities] <br/> <br/>

After taking remediation actions, we were successful in reducing the number of critical vulnerabilities to just one, and the overall vulnerability count has decreased. However, some high and medium vulnerabilities still persist, indicating the need for further assessment and proactive security measures.

By documenting these updated scan results, we aim to emphasize the continuous nature of vulnerability management. It showcases the importance of regularly scanning for vulnerabilities, applying updates, and implementing remediation efforts to enhance the overall security posture of the system. <br/> <br/>

</p>
<b><h2> Conclusion</h2></b>
<p>
  In conclusion, throughout the above scans, we have thoroughly examined the target IP, which was a Windows operating system, using Nessus vulnerability scanning. We successfully identified critical, high, and medium vulnerabilities within the system. By conducting scans with credentials, we gained deeper insights into the system's security posture, enabling us to detect more detailed vulnerabilities.

Furthermore, we explored the significance of installing a deprecated version of Firefox and analyzing its vulnerabilities. This exercise provided valuable lessons in assessing the security risks associated with using unsupported software.

As we progressed, we took proactive measures to remediate some of the vulnerabilities we discovered. Uninstalling the deprecated version of Firefox and updating the system to the latest patches and updates played a crucial role in mitigating certain security risks.

The knowledge gained through these scans is not limited to Windows alone. The experience and understanding we acquired can be applied to other operating systems like the Metasploitable framework and Linux OS. By leveraging Nessus or similar tools, we can effectively scan and identify vulnerabilities on diverse platforms, allowing us to enhance security practices across different environments.

In summary, this project has enabled us to enhance our vulnerability management skills. We have learned the importance of conducting comprehensive scans, leveraging credentials for better assessment, and implementing remediation strategies to improve overall security. By documenting these experiences and insights on GitHub, we hope to contribute to the cybersecurity community's knowledge and encourage proactive vulnerability management practices. <br/> <br/>
</p>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
