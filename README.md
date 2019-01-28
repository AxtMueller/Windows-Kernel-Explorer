# Introduction
Windows Kernel Explorer (you can simply call it as "WKE") is a free but powerful Windows kernel research tool. It supports from Windows XP to Windows 10, 32-bit and 64-bit. Compare to popular tools (such as WIN64AST and PCHunter), WKE is a highly customizable tool and it can run on the latest Windows 10 without updating binary files.

### How WKE works on the latest Windows 10
WKE will automatically download required symbol files if no native support for current system, 90% of the features will work after this step. For some needed data that doesn't exist in symbol files, WKE will try to get them from the DAT file (so, when new Windows 10 releases, I will upload the newest DAT file to GitHub). If there is no internet access for WKE, 50% of the features will still work. Currently, native support is available from Windows XP to Windows 10 RS3, RS4 and RS5 are fully supported by parsing symbol files and DAT file.

### How to customize WKE
You can customize WKE by editing the configuration file. Currently, you can set the device name and symbolic link name of driver, and altitude of filter. You can also enable kernel-mode and user-mode characteristics randomization to avoid being detected by malware. If you rename the EXE file of WKE, then you need to rename SYS/DAT/INI files together with the same name.

### About digital signature
Due to I don't have a digital certificate, I have to use the leaked digital certificate from HT SRL to sign drivers of WKE. I use "DSEFIX" as an alternative solution to bypass DSE, you can try to launch WKE with "WKE_dsefix.bat" if WKE loads driver unsuccessfully on your system. Signing files with the HT SRL digital certificate causes a side effect: almost all anti-virus softwares consider files with HT SRL digital signature are viruses, because many hackers use it to sign malwares since 2015. If you don't trust WKE, you can run it in a test environment, or monitor its network activity on your router.

### About open source
It is a bit awkward, so I say straightforwardly: I don't plan to share the source code of this tool, but I might share some source code of test programs that related to this tool.

# Main Features
1. Process management (Module, Thread, Handle, Memory, Window, Windows Hook, etc.)
2. File management
3. Registry management
4. Kernel-mode callback, filter, timer, NDIS blocks and WFP callout functions management
5. Kernel-mode hook scanning (MSR, EAT, IAT, CODE PATCH, SSDT, SSSDT, IDT, IRP, OBJECT)
6. User-mode hook scanning (Kernel Callback Table, EAT, IAT, CODE PATCH)
7. Memory editor and symbol parser (it looks like a simplified version of WINDBG)
8. Protect process, hide/protect/redirect file or directory, protect registry and falsify registry data
9. Path modification for driver, process and process module
10. Enable/disable some obnoxious Windows components

# Screenshots
In order to optimize the page load speed in low quality network environments, I only placed one picture on this page.
![image](https://raw.githubusercontent.com/AxtMueller/Windows-Kernel-Explorer/master/screenshots/mainmenu.png)
[Click this link to view all screenshots (click middle button to open the page in a new window).](/screenshots/README.md)

# Thanking List
1. Team of WIN64AST (I referenced the UI design and many features of this software)
2. Team of PCHunter (I referenced some features of this software)
3. Team of ProcessHacker (I studied the source code of this software, but I didn’t use it in my project)
4. Author of DSEFIX (I use it as an alternative solution to load driver)

# Cooperation
#### E-MAIL: AxtMueller#gmx.de (Replace # with @)
Please write E-MAIL in English or German, I only reply to E-MAILs that I am interested in.
#### Provided services:
1. Customization: Modify obvious characteristics of WKE and remove all of my personal information in WKE.
2. Implant link: Implant link in WKE on "About" page, every user will see it when main dialog appears.
3. Driver static library: It contains most of main features of WKE.
4. Driver source code: Entire driver source code of WKE.

# [Revision History](/binaries/README.md#all-revision-history)
### Current Version: 20190128
Bug fix: symbol related features in memory editor dialog.  
Bug fix: prompt the status of process and thread in the context menu.  
New feature: disable CreateProcess / CreateThread / LoadImage / Registry / Process and Thread object callbacks, FS filters.  
New feature: support drag file to input box dialog (do not need to type input when you need to fill the file path).  
New feature: highlight hidden drivers and processes.  
New feature: output all object names to a file.  
New feature: display NDIS handler functions.  
New feature: display process command line.  
New feature: registry value editor dialog.  
New feature: hide process, hide driver.  
New feature: unsigned driver loader.  
New feature: hive file operations.  
### Revoked Versions: 00000000
These versions have serious security issues and should not be used anymore.
