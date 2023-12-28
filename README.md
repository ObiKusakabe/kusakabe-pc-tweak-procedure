# My Personal PC Tweaks Procedure

Disclaimer:

This is my personal windows 10 tweaks procedure, I want to make it clear that I am not the owner of, nor do I claim ownership of, any of the original tweak files utilized in this repository. The purpose of this repository is to store all my personal pc tweak and procedure which is what I usually do after installing a fresh installation of windows 10. All credits and rights for the original tweak files go to their respective owners and creators.

This is just a small tweak as most of it has already been done by Atlas OS. 
This personal tweak procedure is made for me, I am not responsible for any failures, errors, or issues that may arise as a result of your use of this procedure, so do at your own risk.

# Procedure

### After a fresh installation of win10 Atlas OS
1.  DDU uninstall driver
2.  install tweaked nvidia driver (nvcleanstall)
3.  tweak nvidia profile inspector also control panel
4.  install process lasso
5.  install park control
6.  MSI utility v3
7.  Interrupt Affinity Policy Tool (set mouse-keyboard-ethernet to core 2, set gpu to core 3 (0 1 2 3))
8.  set power profile to atlas
9.  PowerSettingsExplorer
10. timer resolution (check measure sleep)
11. disable windows game mode

### Registry (!!DON'T FORGET MAKE A REGISTRY BACKUP!!)
1. run disable FSO & Game Bar Support.reg (atlas folder)
2. Enable System Restore.reg (atlas folder)
3. mouse latency (https://n1kobg.blogspot.com/p/blog-page_23.html)
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Input\Settings\ControllerProcessor\CursorSpeed]
"CursorUpdateInterval"=dword:00000001 (MAKE A REGISTRY BACKUP )
4. internet Nagle's Algorithm Tweak (https://n1kobg.blogspot.com/p/blog-page_23.html)
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\{Your NIC's GUID}]
"TcpAckFrequency"=dword:00000001
"TcpDelAckTicks"=dword:00000000
"TCPNoDelay"=dword:00000001
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSMQ\Parameters] 
"TCPNoDelay"=dword:00000001 (MAKE A REGISTRY BACKUP )
6. Priority (https://n1kobg.blogspot.com/p/blog-page_23.html)
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games]
"Affinity"=dword:00000000
"Background Only"="False"
"Clock Rate"=dword:00002710
"GPU Priority"=dword:00000012
"Priority"=dword:00000006
"Scheduling Category"="High"
"SFIO Priority"="High"
"Latency Sensitive"="True"

### Cmd
1. Disable Power Saving.cmd (atlas folder)
2. Disable Sleep.cmd (atlas folder)
3. try timer resolution!!!!!!!!!!!!! (check measure sleep)
   

### Optional
1. check latency by using latency mon software
2. enable printing.cmd (atlas folder)
3. check atlas folder 
