**Configuring a Windows Instance Using EC2Launch for Server 2016**

EC2Launch is a Windows PowerShell scripts which has replaced the (EC2Config service available on windows server 2008 and 2012) on Windows Server 2016. 

EC2Launch performs the following tasks by default upon initial instance boot.

- Sets up new wallpaper that renders information about the instance. (This doesn't apply to Nano Servers.)
- Sets the computer name.
- Sends instance information to the Amazon EC2 console.
- Sends the RDP certificate thumbprint to the EC2 console. (Doesn't apply to Nano Server.)
- Sets a random password for the administrator account.
- Adds DNS suffixes.
Dynamically extends the operating system partition to include any unpartitioned space.
Executes user data (if specified). 
For more information about specifying user data, see Working with Instance User Data.


**Note:** You can also configure EC2Launch to perform these tasks during startup:

- Initialize secondary EBS volumes.
- Send Windows Event logs to the EC2 console logs.
- Send the Windows is ready to use message to the EC2 console.

**Things to consider before installation EC2Lanch**

- If you have already installed and configured EC2Launch on an instance, make a backup of the EC2Launch configuration file. The installation process does not preserve changes in this file. By default, the file is located in the C:\ProgramData\Amazon\EC2-Windows\Launch\Config directory.
- After installing the EC2Launch, 
If you made a backup of the EC2Launch configuration file, copy it to the C:\ProgramData\Amazon\EC2-Windows\Launch\Config directory. (This will replace the existing files there). This step is very important to adhere to.



**To download and install the latest version of EC2Launch**

**See the Link below:**

- Download EC2-Windows-Launch.zip to a directory on the instance.
- Download install.ps1 to the same directory where you downloaded EC2-Windows-Launch.zip.
- Run install.ps1


**Note:** 

- When a Windows Server 2012 having EC2Config already installed not appearing via the RunCommand Instance selection
- First step is to see the version of the Ec2Config service and then Simply Upgrade it.

**Note:** 

- Upon Installation of the EC2Launch Service or EC2Config Service, the server will be avilable in the runcommand instance selection
- If this is not available, check to see if you have AmazonEc2RoleForSSM attached to the instance. 

**Links:**

**EC2Lunch**

- [https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2launch.html#ec2launch-download](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2launch.html#ec2launch-download)

**EC2ConfigService**

- [https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/UsingConfig_Install.html ](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/UsingConfig_Install.html )