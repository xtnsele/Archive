**Implementation of N2WS Veeam Cloud Protection Manager (CPM) 2.3.0d**

**Part 1** 

Click on the Lunch instance Menu
Under AWS Market place, select the right version (here I will be selecting the free-tier for testing)

**Step 1**. Cloud Protection Manager Free Edition

**Note:** You can select whatsoever edition is applicable to you from here. In the future after testing I will have to use a different Edition to support my need.

When this AMI is selected, this will be prompted below to show the product details etc. 

**Step 2:** Select the instance type

**Step 3:** Select all right Instance configuration Details,
Such as Network, subnet, IAM role, etc. 

**Step 4:** Add storage 
Add Tags additionally in the next steps (not applicable to me)

**Step 5:** Select an existing Security Group or Create a new Security group

**Step 6:** Now review and relaunch. This is basically how an EC2 instance is created. 
Note: Remember to create a new keypair or select an existing keypair or else, you wouldn’t be able to access this newly created instance and download this keypair.

**Step 7:** Finally click on launch this instance.
Locate the newly created EC2 instance and associate it with an EIP Address. (This is needed in order to be able to connect to it over the internet)



**Part. 2**

Create a role for AWS permission/roles for CPM Operation
- See my blog for this: [https://techtrainingworld.wordpress.com/ ](https://techtrainingworld.wordpress.com/ )

**Part 3:**

Access the URL or Public IP via any Web browser in this format; https://PublicIPAddress or https://URLdefined
See blog for additional information on how to configure backup and recover backup: https://techtrainingworld.wordpress.com/ 

Note: We are using HTTPS because this is the defined protocol we selected with configuring the CPM. 

**Note:** The default username for N2WS Veeam CPM is: cpmuser
and ensure you have the the private key in place needed to authenticate as well. Simply load the .pem file into PuTTYGen and download the private key.
- See my blog for these steps [https://techtrainingworld.wordpress.com/ ](https://techtrainingworld.wordpress.com/ )