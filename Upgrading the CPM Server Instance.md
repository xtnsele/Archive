**Upgrading the CPM Server Instance**

**These are the steps**

To upgrade/restart the CPM Server Instance:

1.	Launch a new CPM Server instance in the same region and AZ as the old one. You can launch the instance using also from the link here [https://aws.amazon.com/marketplace/library?ref=cns_lclkLib](https://aws.amazon.com/marketplace/library?ref=cns_lclkLib) 

To determine the AZ of the new instance or to launch it in a Virtual Private Cloud (VPC) subnet, launch the instance using the EC2 console rather than using the 1-click option.

Terminate the old instance, preferably while no backup is being performed. Wait until it is in the terminated state i order to be able to use the same Private IP address on the new instance. 

**Note:** Go to the Volumes view in the AWS Management Console and create a snapshot of the CPM data volume. The volume is typically named CPM Cloud Protection Manager Data. The snapshot is only needed in the event there is a problem with the upgrade process and it can be deleted afterwards.

**1**.	When the new instance is in the running state, connect to it with a browser using HTTPS to the configured uRL or Public IP Address.

**2**.	Approve the exception to the SSL certificate if this has not been configured yet.

**3**.	Choose Use Existing Data Volume and paste in your AWS credentials.

**4**.	Select your old data volume from the list of volumes to complete the configuration process. Operations will resume automatically.

If you are using backup scripts that utilize SSH, you may need to login to the CPM Server once and run the scripts manually, so the use of the private key will be approved.
