**Updated AWS Network Adapter "Redhat to Cirix PV upgrade"**

**Note:** The goal of this task is to upgrade from "Redhat to Cirix PV" and then from Cirix PV to AWS PV Drivers"

**Prerequisite**

- Ensure you have the latest EC2Config services running on the server

- Ensure you have the PowerShell framework 2.0 installed (Windows Management Framework)
https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2config-version-details.html

**To upgrade Redhat drivers**

1. Connect to your instance and log in as the local administrator. For more information about connecting to your instance, see Connecting to Your Windows Instance.

2. In your instance, download the Citrix PV upgrade package.

3. Extract the contents of the upgrade package to a location of your choice.

4. Double-click the Upgrade.bat file. If you get a security warning, choose Run.
 
5. In the Upgrade Drivers dialog box, review the information and choose Yes if you are ready to start the upgrade.

6. In the Red Hat Paravirtualized Xen Drivers for Windows uninstaller dialog box, choose Yes to remove the RedHat software. Your instance will be rebooted.

**Note:**- If you do not see the uninstaller dialog box, choose Red Hat Paravirtualize in the Windows taskbar.
Check that the instance has rebooted and is ready to be used.

This can be verified from the EC2 console at [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/)

Select the Instances, right-click on it and on Instance settings, right click and and then select Get System Log.

The upgrade operations should have restarted the server 3 or 4 times. You can see this in the log file by the number of times Windows is Ready to use is displayed.

-  Connect to your instance and log in as the local administrator.
- Close the Red Hat Paravirtualized Xen Drivers for Windows uninstaller dialog box.
- Confirm that the installation is complete. Navigate to the Citrix-WIN_PV folder that you extracted earlier, open the PVUpgrade.log file, and then check for the text installation is complete.



**Upgrading from Citric PV driver to AWS PV drive**

**Prerequisite**

- Ensure you create an AMI of the instance first (For possible "roll back")
 
- Ensure you have Microsoft .NET Framework 4.5  installed on the server
[https://www.microsoft.com/en-us/download/details.aspx?id=30653&6B49FDFB-8E5B-4B07-BC31-15695C5A2143=1](https://www.microsoft.com/en-us/download/details.aspx?id=30653&6B49FDFB-8E5B-4B07-BC31-15695C5A2143=1)

**Step 2:**
Ensure you download the latest AWS PV drive from this link [https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Upgrading_PV_drivers.html](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Upgrading_PV_drivers.html)

1. Download the latest driver package to the instance.

2. Extract the contents of the folder and then run AWSPVDriverSetup.msi.

3. Then follow the Instruction steps as it basically a next and select process (selct "i am ready" and as well as "i agree" follow by the many next windows :).


**FYI:** After running the MSI, the instance automatically reboots and then upgrades the driver. The instance will not be available for up to 15 minutes. After the upgrade is complete and the instance passes both health checks in the Amazon EC2 console, connect to the instance using Remote Desktop and verify that the new driver was installed. In Device Manager, under Storage Controllers, locate AWS PV Storage Host Adapter. Verify that the driver version is the same as the latest version listed in the Driver Version History table.

Links:
-[ https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Upgrading_PV_drivers.html#aws-pv-upgrade]( https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Upgrading_PV_drivers.html#aws-pv-upgrade)
- [https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Upgrading_PV_drivers.html#aws-pv-upgrade](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Upgrading_PV_drivers.html#aws-pv-upgrade)