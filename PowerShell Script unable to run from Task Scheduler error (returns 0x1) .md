**PowerShell Script unable to run from Task Scheduler (returns 0x1) error**

**Note:** When you have restricted mode enabled on PowerShell,
‌PowerShell executionpolicy was currently set to restricted, thereby making the PowerShell backup script not to execute properly.

[https://blog.netspi.com/15-ways-to-bypass-the-powershell-execution-policy/](https://blog.netspi.com/15-ways-to-bypass-the-powershell-execution-policy/)

**To verify this**

Run the PowerShell script and Get-Executionpolicy
--> This displayed that PowerShell is currently in a restricted mode

**To resolve this:**
set-executionpolicy -executionpolicy unrestricted

[https://social.technet.microsoft.com/Forums/ie/en-US/68af42d6-7a12-49eb-941c-72ba0cc6d316/setexecutionpolicy-unrestricted-force?forum=winserverpowershell](https://social.technet.microsoft.com/Forums/ie/en-US/68af42d6-7a12-49eb-941c-72ba0cc6d316/setexecutionpolicy-unrestricted-force?forum=winserverpowershell)
