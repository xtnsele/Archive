**Delete old/unwanted updates from WSUS**

Classification of such as updates, drivers, Update Rollups, Critical Updates etc. from the WSUS database
- Note even when you decline updates and use the wsus cleanup wizard, it still shows up in the WSUS database (SUSDB)


**What this script does**! 
It will delete it a few each time or does it query the database for all updates first before it starts to delete.


*Run from PowerShell*

$wsus = [Microsoft.UpdateServices.Administration.AdminProxy]::getUpdateServer() 


$wsus.getupdates() | Where {$_.UpdateClassificationTitle -eq 'Drivers'} | ForEach-Object { $wsus.DeleteUpdate($_.Id.UpdateID); Write-Host $_.Title removed }


[http://runesk.blogspot.de/2012/09/delete-oldunwanted-updates-from-wsus.html](http://runesk.blogspot.de/2012/09/delete-oldunwanted-updates-from-wsus.html)


------------------------------------------------

Windows Commandlets
‌‌Get-Command -Module UpdateServices

**1**. Invoke-WSUSServerCleanup
--> Need to clean obsolete updates

Get-WsusServer | Invoke-WsusServerCleanup -CleanupObsoleteComputers –CleanupObsoleteUpdates


**2**. Get-WsusUpdate, Approve-WsusUpdate, and Deny-WsusUpdate
Last on the list are the three cmdlets that represent the update management. Get/Approve/Deny-WsusUpdate allows you to find updates and approve or decline the updates on the WSUS server. By using Get-WsusUpdate, you can filter for what types of updates you want to look at for approval or to decline. To see a list of all updates that haven’t been approved and are needed by your systems, you can run the following command:

Get-WsusUpdate -Approval Unapproved -Status Needed
