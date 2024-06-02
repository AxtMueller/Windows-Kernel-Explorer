# Introduction
Windows Kernel Explorer (you can simply call it as "WKE") is a free but powerful kernel research tool. It supports from Windows XP to Windows 11. Compared with WIN64AST and PCHunter, WKE can run on the latest Windows without updating binary files. This means that even if I do not update WKE, or you do not have the latest version of WKE, old WKE can still run on new Windows and most features will function normally.

### How does WKE work on the latest Windows
WKE automatically downloads requisite symbol files if the current system is not supported natively, 90% of the features will be available after this step. For some needed data that doesn't exist in symbol files, WKE tries to retrieve them from the DAT file (when new Windows releases, I will upload a new DAT file to GitHub). Even if WKE is not able to connect to the internet and the DAT file does not exist, more than half of the features will still work. At present, native support is available from Windows XP to Windows 10 RS3. Windows 10 from RS4 to the lastest Windows 11 are fully supported by parsing symbol files and DAT file.

### How to customize WKE
You can customize WKE by editing the configuration file. Currently, you can specify the device name and symbolic link name of driver, and altitude of filter. You can also enable kernel-mode and user-mode characteristics randomization to avoid being detected by malware. If you rename the EXE file of WKE, you must synchronously rename SYS/DAT/INI files with the same name as the EXE file.

### About digital signature and negative comments from Anti-Virus software
Because I don't have my own digital certificate, I have to use a leaked digital certificate to sign my drivers. Signing files with leaked digital certificates has a side effect: many Anti-Virus software infer files with leaked digital signature are suspicious, because many hackers use leaked digital certificates to sign malware. I don't care about any negative comments from any Anti-Virus software, the rule is simple: if you don't trust a program, just don't use it.

### About WKE can be detected by Anti-Cheat solutions
WKE is not designed to bypass any Anti-Cheat solution. If you want to use WKE in a specfic environment, please order "binary customization" service.

### About loading driver unsuccessfully
If WKE prompts "unable to load driver", there may be the following reasons:
###### 1. HVCI is enabled.  
###### 2. Anti-Virus software prevents the driver from loading.  
Solutions:
###### 1. [Disable HVCI](https://docs.microsoft.com/en-us/windows/security/threat-protection/device-guard/enable-virtualization-based-protection-of-code-integrity#how-to-turn-off-hvci) or disable Secure Boot.  
###### 2. Add the files of WKE to the whitelist of the Anti-Virus software.  

### About deleting files or folders unsuccessfully
NTFS parsing is turned on by default on systems from Windows XP to Windows 10. On some systems, parsing NTFS fails and causes deletion of files or folders to fail. In this case, you must turn off "NTFS parsing" in "Software Options" to delete files and folders.  

# Main Features
1. Process management (Module, Thread, Handle, Memory, Window, Windows Hook, etc.)
2. File management (NTFS partition analysis, low-level disk access, etc.)
3. Registry management and HIVE file operation
4. Kernel-mode callback, filter, timer, NDIS blocks and WFP callout functions management
5. Kernel-mode hook scanning (MSR, EAT, IAT, CODE PATCH, SSDT, SSSDT, IDT, IRP, OBJECT)
6. User-mode hook scanning (Kernel Callback Table, EAT, IAT, CODE PATCH)
7. Memory editor and symbol parser (it looks like a simplified version of WINDBG)
8. Hide driver, hide/protect process, hide/protect/redirect file or directory, protect registry and falsify registry data
9. Path modification for driver, process and process module
10. Enable/disable some obnoxious Windows components

# [Screenshots](/screenshots/README.md)
In order to optimize the page load speed in low quality network environments, I only placed one picture on this page.
![image](https://raw.githubusercontent.com/AxtMueller/Windows-Kernel-Explorer/master/screenshots/mainmenu.png)

# Thanking List
1. Team of WIN64AST: I referenced the UI design and many features of this software.
2. Team of PCHunter: I referenced some features of this software.
3. Team of ProcessHacker: I studied the source code of this software, but I didn't use it in my project.
4. Donald John Trump: Ich hoffe sehr, dass er noch vier Jahre Präsident sein kann.

# Contact
### E-MAIL: AxtMueller#gmx.de (Replace # with @)
1. If you find bugs, have constructive suggestions or would like to purchase a paid service, please let me know.  
2. You'd better write E-MAIL in English or German, I only reply to E-MAILs that I am interested in.
3. In order to disclose as little personal information as possible (IP address, online time, etc.), I do not use instant messaging. Just write what you want in the E-MAIL.
4. In order to reduce the impact of the Internet on real life, I also do not use Facebook, Twitter, etc. Please don't ask me for such information via E-MAIL.
### Paid services:
1. Binary customization: You will get a customized version of WKE without copyright information and digital signature, this will prevent some software from detecting WKE based on the program characteristics. Add your customized copyright information and sign files with a different certificate than the public version is also possible. The customized version of WKE is without VMP, so it can be run on 64-bit Windows with HVCI enabled. 
2. Partial source code acquisition: You will get the source code of specific features that you are interested in.
3. Complete source code acquisition: You will get the complete source code for both EXE and SYS.
4. Software production: Write the user-mode program or kernel-mode driver according to your needs. This service is only available to customers who have purchased any of the above services.

# [Revision History](/binaries/README.md#all-revision-history)
### Current Version: 20240210
Bug fix: Update checking failure.  
New feature: Windows 11 22631 is supported.
### Revoked Versions: 00000000
These versions have serious security issues and should not be used anymore.
