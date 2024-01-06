# My Personal PC Tweak Procedure

Disclaimer:

This is my personal windows 10 tweak procedure, I want to make it clear that I am not the owner of, nor do I claim ownership of, any of the original tweak files utilized in this repository. The purpose of this repository is to store all files needed to tweak my pc and tweak procedure which is what I usually do after installing a fresh installation of windows 10. All credits and rights for the original tweak files go to their respective owners and creators.

This is just a small tweak as most of it has already been done by Atlas OS. 
This personal tweak procedure is made for me, I am not responsible for any failures, errors, or issues that may arise as a result of your use of this procedure, so do at your own risk.

### Tweak Procedure
1.  Uninstall driver using [Display Driver Uninstaller (DDU)](https://www.guru3d.com/download/display-driver-uninstaller-download/) 
2.  Install tweaked nvidia driver using [NVCleanstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/)
3.  Tweak control panel and [nvidiaProfileInspector](https://github.com/Orbmu2k/nvidiaProfileInspector/releases)
4.  Install [Process Lasso](https://bitsum.com/get-lasso-pro/)
5.  Install [ParkControl](https://bitsum.com/parkcontrol/)
6.  set the gpu interrupt priority to high using [MSI Utility v3](https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/)
7.  set mouse-keyboard-ethernet to core 2, set gpu to core 3  using [Microsoft Interrupt Affinity Tool](https://www.techpowerup.com/download/microsoft-interrupt-affinity-tool/) (note: cores start from 0)
8.  Set power profile to default/atlasOS power plan (windows settings)
9.  set your current active power plan scheme AC value to 5000 in the "Processor performance time check interval" setting which is in the "Processor power management" subgroup using [PowerSettingsExplorer](https://forums.guru3d.com/threads/windows-power-plan-settings-explorer-utility.416058/)
10. Timer resolution (check measure sleep)
11. Disable windows game mode (windows settings)

### Registry (!!DON'T FORGET MAKE A REGISTRY BACKUP!!)
1. Run disable FSO & Game Bar Support.reg (atlasOS folder)
2. Enable System Restore.reg (atlasOS folder)
3. Mouse latency (https://n1kobg.blogspot.com/p/blog-page_23.html)
>[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Input\Settings\ControllerProcessor\CursorSpeed]  
>"CursorUpdateInterval"=dword:00000001
4. Internet Nagle's Algorithm Tweak (https://n1kobg.blogspot.com/p/blog-page_23.html)
>[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\{Your NIC's GUID}]  
>"TcpAckFrequency"=dword:00000001  
>"TcpDelAckTicks"=dword:00000000  
>"TCPNoDelay"=dword:00000001
  
>[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSMQ\Parameters]  
>"TCPNoDelay"=dword:00000001
5. Priority (https://n1kobg.blogspot.com/p/blog-page_23.html)
>[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Audio]  
>"Affinity"=dword:00000007  
>"Background Only"="True"  
>"Clock Rate"=dword:00002710  
>"GPU Priority"=dword:00000008  
>"Priority"=dword:00000006  
>"Scheduling Category"="Medium"  
>"SFIO Priority"="Normal"

>[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\DisplayPostProcessing]  
>"Affinity"=dword:00000000  
>"Background Only"="True"  
>"BackgroundPriority"=dword:00000018  
>"Clock Rate"=dword:00002710  
>"GPU Priority"=dword:00000012  
>"Priority"=dword:00000008  
>"Scheduling Category"="High"  
>"SFIO Priority"="High"  
>"Latency Sensitive"="True"  
  
>[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games]  
>"Affinity"=dword:00000000  
>"Background Only"="False"  
>"Clock Rate"=dword:00002710  
>"GPU Priority"=dword:00000012  
>"Priority"=dword:00000006  
>"Scheduling Category"="High"  
>"SFIO Priority"="High"  
>"Latency Sensitive"="True"  

### CMD run as Admin
1. Disable Power Saving.cmd (atlasOS folder)
2. Disable Sleep.cmd (atlasOS folder)
   

### Optional
1. Check latency by using [LatencyMon](https://www.resplendence.com/latencymon) software
2. Enable printing.cmd (atlas folder)
3. Check atlasOS folder
4. Try [TimerResolution](https://github.com/amitxv/TimerResolution) (also check "measure sleep" because timerResolution won't work on Windows 10 2004 and higher version, but i've heard it work windows 11)
