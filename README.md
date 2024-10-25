## Introduction

**Windows Prefetch File Analysis Project**

![image](https://github.com/user-attachments/assets/a860292b-fe81-4e0d-8dee-683fdcd84685)

*Platforms and Technologies Used:* Windows, FTK Imager, WinPrefetchView, Autopsy, Excel  
*Languages Used:* Python, PowerShell

In this project, I conducted a forensic analysis of Windows prefetch files to extract critical data regarding program execution and system activity. Utilizing tools like FTK Imager and WinPrefetchView, I traced user activity, identified suspicious processes, and gathered evidence related to potential malware or unauthorized actions. By reconstructing a timeline of program usage, I correlated these events with possible security incidents, enhancing my forensic investigation skills. This project deepened my understanding of Windows-based forensic investigations and strengthened my ability to detect compromised systems.

*Step 1: Set up your analysis VM*
- Download and instal a free trial of VMware or any hypervisor one of your choice
- Download and deploy a free Windows 11 VM from Microsoft
- Run this command on an Administrative PowerShell

```powershell IEX (New-Object Net.WebClient).DownloadString("https://ec-blog.s3.us-east-1.amazonaws.com/DFIR-Lab/PF_Lab/prep_lab.ps1") ```

This command automatically installs DotNet 6, Eric Zimmerman's tools and downloads the forensic evidence, we can double-check this by viewing ```C:\Cases\Prefetch ```


*Step 2: Create a Prefetch Timeline*
- Using Administrative PowerShell and the following command:
  ``` C:\DFIR_Tools\ZimmermanTools\net6\PECmd.exe -q -d C:\Cases\Prefetch\ --csv "C:\Cases\Analysis\" --csvf prefetch.csv ```
  
