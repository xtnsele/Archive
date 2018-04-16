**Windows 2016 Servers does not show up on WSUS console**

Environment WSUS is installed

- WSUS is installed on Windows 2012 R2

**Scenario**
All other servers are reporting to WSUS such as Windows server 2008R2 and Server 2012 R2 but Windows Server 2016 does not.

Note: All registry key are created on Server 2016 and there is connectivity between the wsus server and the windows server.
- All SusClientID and SusClientIDvalidation keys are deleted from the registry because the sever was created from a clown (AMI)



**Solution**

- Stop windows update service
- `Delete SoftwareDistribution folder (C:\Windows\SoftwareDistribution folder)`
- wuauclt /resetauthorization /detectnow
- wuacult /reportnow /detectnow

This can take a little while (from my scenario wasn't so long)

[https://community.spiceworks.com/topic/1652153-computers-not-yet-reported-0](https://community.spiceworks.com/topic/1652153-computers-not-yet-reported-0) 
[https://www.reddit.com/r/homelab/comments/5q99dp/windows_10_1607_clients_do_not_report_to_wsus_on/](https://www.reddit.com/r/homelab/comments/5q99dp/windows_10_1607_clients_do_not_report_to_wsus_on/) 