# Introduction
Windows Kernel Explorer (you can simply call it as "WKE") is a free but powerful Windows kernel research tool. It supports from Windows XP to Windows 10, 32-bit and 64-bit. Compare to popular tools (such as WIN64AST and PCHunter), WKE is a highly customizable tool and it can run on the latest Windows 10 without updating binary files.

### How WKE works on the latest Windows 10
WKE will automatically download required symbol files if no native support for current system, 90% of the features will work after this step. For some needed data that doesn't exist in symbol files, WKE will try to get them from the DAT file (so, when new Windows 10 releases, I will upload the newest DAT file to GitHub). If there is no internet access for WKE, 50% of the features will still work. Currently, native support is available from Windows XP to Windows 10 RS3, RS4 and RS5 are fully supported by parsing symbol files and DAT file.

### How to customize WKE
You can customize WKE by editing the configuration file. Currently, you can set the device name and symbolic link name of driver, and altitude of filter. You can also enable kernel-mode and user-mode characteristics randomization to avoid being detected by malware. If you rename the EXE file of WKE, then you need to rename SYS/DAT/INI files together with the same name.

### About digital signature
Due to I don't have a digital certificate, I have to use the leaked digital certificate from HT SRL to sign drivers of WKE. I use "DSEFIX" as an alternative solution to bypass DSE, you can try to launch WKE with "WKE_dsefix.bat" if WKE loads driver unsuccessfully on your system. Signing files with the HT SRL digital certificate causes a side effect: almost all anti-virus softwares consider files with HT SRL digital signature are viruses, because many hackers use it to sign malwares since 2015. If you don't trust WKE, you can run it in a test environment, or monitor its network activity on your router.

### About open source
It is a bit awkward, so I said straightforwardly: I don't plan to share the source code of this tool, but I might share some source code of test programs that related to this tool.

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
In order to optimize the page load speed in low quality network environments, I don't place pictures on this page.
#### [Click this link to view screenshots.](/screenshots/README.md)

# Thanking List
1. Team of WIN64AST (I referenced the UI design and many features of this software)
2. Team of PCHunter (I referenced some features of this software)
3. Team of ProcessHacker (I studied the source code of this software, but I didn’t use it in my project)
4. Author of DSEFIX (I use it as an alternative solution to load driver)

# Contact Me
#### My EMAIL address is AxtMueller#gmx.de (Replace # with @).
Please write EMAIL in English or German, I only reply to EMAILs that I am interested in.

# Revision History
### Current Version: 20181231
This is the first public version.
#### Revoked Versions: 00000000
These versions have serious security issues and should not be used anymore.
