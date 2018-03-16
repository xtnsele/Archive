**Registry Settings for configuring WSUS Clients to get Updates from the WSUS server**

The below syntax should be saved with the .reg extension and run  in order to create the registry keys.


    Windows Registry Editor Version 5.00
    
    [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate]
    "ElevateNonAdmins"=dword:00000001
    "WUServer"="http://x.x.x.x:8530"
    "WUStatusServer"="http://x.x.x.x6:8530"
    
    [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU]
    "NoAutoUpdate"=dword:00000000
    "AUOptions"=dword:00000003
    "ScheduledInstallDay"=dword:00000000
    "ScheduledInstallTime"=dword:0000000f
    "AutoInstallMinorUpdates"=dword:00000001
    "UseWUServer"=dword:00000001