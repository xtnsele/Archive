**Delete ADFS windows internal database without access credentials?**

Having issues overwriting the WID, simply perform either of the two steps. There are 2 ways to get rid of ADFS database,

**Delete ADFS database using SQL connection**
Since MS-SQL is not previously installed, install this and connect to it.

-Install Microsoft SQL Server 2012 Express
- Connect to windows internal database using “\\.\pipe\MICROSOFT##WID\tsql\query”
- Now delete AdfsArtifactStore and AdfsConfiguration database


In case you do not have access to windows internal database take 2nd option.
In my case i used this option below (Uninstall Windows Internal Database feature)


Go to Server Manager 

- Manage 
- Remove Roles and Features
Now go to roles select “Active Directory Federation Service” and 
- click next and select “Windows Internal Database” under features
Click next and finish the uninstall.

**Note:** Before we can install roles and features back again we have to delete the database files.

Open a CMD and run the command below

del C:\Windows\WID\data\adfs*