**Uninstall Oracle Database 11G or 12c**

The process of uninstalling Oracle Database 12c is very similar to that of Oracle Database 11g.


**Delete the Associated Environment Variable**

Deleting environment variable would definitely mitigate a whole lots of errors if your plan to re-install the oracle software. 

Many times installation gets stuck due to PRVF-3929 error stating that “Environment variable path is too long”. In order to avoid this error and to ensure glitch free installation of Oracle software it’s recommended to delete the environment variable entry of your Oracle Home.


**How to Delete Environment Variable**

Right Click your Computer Icons and Select “Properties”. Then from the left hand side panel of the System Properties Windows Select “Advance System Settings”. This will open up “System Properties” Windows.

Inside the “System Properties” Windows go to “Advance” Tab and select “Environment Variable” 

On the “Environment Variable” Window inside the “System Variable Section” Find entry with the name “Path”, then double click and open it. Doing so will open up an “Edit System Variable” dialogue box. On that dialogue box under the “Variable value field” find your Oracle Home entry and Delete it.

    C:\oracle\product\11.2.0\bin

    C:\oracle\product\OPatch\ 

**Step 2: Delete Registries**

During the installation, oracle database makes some registries in windows system to store the information of its configurations as well as for proper functioning of Oracle Windows Services. To Uninstall Oracle Database 12c completely from your system you need to properly stop all the Oracle database services which run in the background. Also if you are planning for re-installing the Oracle Database software then you also need to delete all the configuration settings.

In short to ensure the smooth and errorless re-installation of any version of oracle database software, without formatting your computer system, you need to delete all the Oracle Database Registries.

Registries are very fragile part of any windows system thus messing with them can be catastrophic and can harm your system therefore be careful while deleting them. I would highly suggest you to take their backup.


**How to Delete the Oracle Registries**

To delete any registry you need to first access them and in windows all the registries are placed inside the “Registry Editors”. To access the Registry Editor first open up your Run Dialogue Box by pressing Run Windows Key and ‘R’ key simultaneously or you can directly search RUN in your start menu.

From the run window or search button, type 

    regedit.exe

Once you have your Run Dialogue box opened then write “regedit” into it and press enter. This will open your “Registry Editor”.

Now first we have to delete the “Oracle Software” Registry. To access this registry first go to HKEY_LOCAL_MACHINE and then go to sub directory SOFTWARE. Under the software – search for directory “Oracle”. Once you have reached this directory, right click and Delete it.

    HKEY_LOCAL_MACHINE --> SOFTWARE --> ORACLE
    
Next we have to delete all the registries for Oracle Database Services. To access these registries first go to HKEY_LOCAL_MACHINE and then go to sub directory “Systems” then “CurrentControlSet” and then “Services”. Under the Services directory you have to find all the Registries which are responsible for your oracle database services. If Oracle Database 12c is the only product from Oracle that is installed on your system then search for all the registries whose names start with Oracle and Delete them. If you have other products from Oracle installed on your system then be careful and delete accordingly. In the screenshot below you can see some general Oracle Service Registries.

    HKEY_LOCAL_MACHINE → SYSTEM → CurrentControlSet → SERVICES

**Restart your system**.
Next you have to restart your system so that your operating system can blend in all the settings which we just altered


**Delete the Oracle Home Directory**

An Oracle home is a directory into which all Oracle software is installed. Once you have deleted all the registries of oracle database 12c you are free to delete oracle home directory from your system. In order to delete Oracle Home open up your computer and go to your C drive as well as any other drive where you have installed your oracle database 12c. Now go to APP directory then to the directory with your username here select all the files and delete them. If you want to save backups then do not delete flash_recovery_area.

If in case your folder is not getting deleted then don’t worry. First try to refresh your system or you can also reboot the system then try deleting again. If it is still not deleting then re-check the services and registries and see whether you have deleted all the oracle registries or not. If not then delete those that are still left and then try deleting the Oracle database folder again.


**Delete Directory from Program File**

Next go to your program file directory and search for folder with the name Oracle. I have one here and then delete it.

**Delete Directory from Start Menu**

Next you have to delete the directory from start menu. For that go to “`C:\ProgramData\Microsoft\Windows\Start Menu\Programs`” and here search for your Oracle Folder and delete it.

**Clear the Temporary files and Recycle bin**

Again open your Run dialogue box and write %temp% this will open the temporary folder and here delete all the files. Next come to your desktop and empty your recycle bin.

**Delete the Oracle user**

Next and the last step is to delete the oracle home user which we created during the installation of the oracle database. In order to do so, right click “Computer Icon” and select “Manage”. Inside the computer management window click “Local User Groups” and then click and open “Users” folders. From the list of the user you can delete the ones which you have created as an oracle home user during the installation. In my case its RebellionRider, Right click and Select Delete.









[https://stackoverflow.com/questions/8450726/how-to-uninstall-completely-remove-oracle-11g-client](https://stackoverflow.com/questions/8450726/how-to-uninstall-completely-remove-oracle-11g-client)

[http://www.rebellionrider.com/oracle-database-12c-tutorial/how-to-uninstall-oracle-database-12c-rebellionrider.htm#.Ww_akEiFOUn](http://www.rebellionrider.com/oracle-database-12c-tutorial/how-to-uninstall-oracle-database-12c-rebellionrider.htm#.Ww_akEiFOUn)