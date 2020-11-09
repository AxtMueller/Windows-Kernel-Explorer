# Introduction
These EXE files ([WKE32](https://github.com/AxtMueller/Windows-Kernel-Explorer/raw/master/binaries/WKE32.exe) / [WKE64](https://github.com/AxtMueller/Windows-Kernel-Explorer/raw/master/binaries/WKE64.exe)) are packaged by WINRAR and they will automatically decompress files after execution. You can rename these EXE files to ZIP files and decompress ZIP files manually.   

# Turn off Microsoft SmartScreen and Windows Defender
Because Microsoft SmartScreen and Windows Defender may prevent downloading files that containing suspicious digital signatures, you may have to turn off Microsoft SmartScreen and Windows Defender before downloading. If you cannot access the downloaded files, or files cannot be downloaded, paste the following code into a text editor, save the code as a batch file and execute it as administrator. After restarting, this page will be opened again.
```
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f
reg add "HKLM\Software\Policies\Microsoft\Windows Defender" /v DisableAntiVirus /t REG_DWORD /d 1 /f
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Real-Time Protection" /v DisableIOAVProtection /t REG_DWORD /d 1 /f
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Real-Time Protection" /v DisableRealtimeMonitoring /t REG_DWORD /d 1 /f
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Real-Time Protection" /v DisableBehaviorMonitoring /t REG_DWORD /d 1 /f
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Real-Time Protection" /v DisableOnAccessProtection /t REG_DWORD /d 1 /f
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Real-Time Protection" /v DisableScanOnRealtimeEnable /t REG_DWORD /d 1 /f
reg add "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer" /v SmartScreenEnabled /t REG_SZ /d "Off" /f
reg add "HKCU\SOFTWARE\Microsoft\Edge\SmartScreenEnabled" /v "" /t REG_DWORD /d 0 /f
reg add "HKCU\SOFTWARE\Microsoft\Edge\SmartScreenPuaEnabled" /v "" /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\CurrentVersion\AppContainer\Storage\microsoft.microsoftedge_8wekyb3d8bbwe\MicrosoftEdge\PhishingFilter" /v EnabledV9 /t REG_DWORD /d 0 /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce" /v OpenURL /t REG_SZ /d "explorer.exe https://github.com/AxtMueller/Windows-Kernel-Explorer/tree/master/binaries" /f
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\RunOnce" /v OpenURL2 /t REG_SZ /d "%HOMEDRIVE%\program files\internet explorer\iexplore.exe \"https://github.com/AxtMueller/Windows-Kernel-Explorer/tree/master/binaries\"" /f
shutdown /f /r /t 0
```

# All revision history
### 10th version: 20201111
[This is the latest version.](../README.md#revision-history)
### 9th version: 20200610
Bug fix: Thread entry point cannot be displayed properly in some versions of Windows 7.  
Bug fix: LoadImageNotify cannot be enumerated in some versions of Windows 8.  
New feature: Output tree view of device stacks to a text file.  
New feature: Add a description for GDT items.  
Off topic: This version was originally planned to be released on June 1, but due to the Killing of George Floyd, my attention was attracted, which led to the release of this version 10 days later than the original plan. George Floyd’s death is a tragedy, but this is just one of countless tragedies that have been caused since the establishment of the United States. The US government is oppressing the American people, slaughtering the people of the Middle East, committing economic terrorism against countries that refuse to cooperate with it, and bullying European countries. It has caused much more harm to all mankind than Nazi Germany and Communism Soviet Union. Only when this evil regime is completely destroyed can cease such tragedies to occur.
### 8th version: 20200107
Bug fix: Inputbox works improperly on the latest Windows 10.  
### 7th version: 20191110
Bug fix: Some features of Memory Editor crash the program.  
### 6th version: 20191104
Bug fix: UI fine-tuning (menu, listview, etc).  
Bug fix: Optimize the "export to file" feature.  
Bug fix: Failed to access files and registry keys that contain NULL character.  
New feature: Map physical memory (Memory Editor).  
### 5th version: 20190329
Bug fix: file operation failure in FAT32 partition.  
New feature: export all text in the list view to a file.  
### 4th version: 20190326
Bug fix: UI fine-tuning.  
Bug fix: Repackage the binaries with the latest data file.  
### 3rd version: 20190325
Bug fix: UI optimization (adjust list view spacing from 13 pixels to 16 pixels, display process icon).  
Bug fix: some code modifications cannot be detected under certain circumstances.  
Bug fix: some directories cannot be deleted under certain circumstances.  
New feature: driver uninstallation.  
New feature: directory replication.  
New feature: digital signature verification.  
New feature: file CRC32 and MD5 calculations.  
New feature: NTFS partition parsing and stream enumeration.  
### 2nd version: 20190128
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
### 1st version: 20181231
This is the first public version.
