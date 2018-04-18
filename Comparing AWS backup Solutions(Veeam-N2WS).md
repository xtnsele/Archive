**Backing Up AWS Instances**

(Brief comparison between pulling and AMI from an Instance or using a backup solution (Veeam [N2WS]))

**AMI**

**Note:** Pulling an AMI is not a backup solution
- The most easiest and it is simply by creating an AMI of the instance (and with this you will have to launch an instance with the created AMI). 

This is a bit time consuming as you will have to disassociate the other instance EIP and Private IP and use it in creating a new instance with the taken AMI).
**Note:** other factors are also considered such as the VPC, Subnet and Security groups etc.

You are only charged for the bits that make up the AMI
- No charge for creating AMI, but if you're making it from a running instance you will pay the fees for running a micro instance (which is about $0.02/hr, depending on  the availability region
- When storing the AMI, For S3- Backup AMI, you only pay for the S3 storage
- So you are only charge for the cost of storing the snapshot of the volume (see pricing here: https://aws.amazon.com/ebs/pricing/)


**N2WS**

AWS provides a robust cloud platform for customers to create and deploy business applications without the financial burdens and time commitments of on-premises data centers. But regardless of the platform — in the cloud or on-premises — your applications and data are your responsibility (therefore plan a better backup solution for it).


N2WS, a Veeam Company which provides enterprise-class data protection that is purpose-built for AWS workloads. 
This operational backup, recovery and disaster recovery (DR) solution provided by Veaam is called Cloud Protection Manager. This includes full support for Amazon EC2 instances, EBS volumes, RDS, Redshift & Aurora clusters etc. by extending and enhancing native Amazon snapshots and delivering fast and reliable recovery of complete instances, specific volumes and even individual files, in seconds.

This solution is currently being used by Oracle, Cisco, CocaCola, Southwest and Harvard University etc..





**Advantages of using N2WS Backup solutions**

- Cloud Protection Manager provides recovery access to data as quickly as possible (24/7) and enables backup as many times as needed. 
- Cloud Protection Manager leverages native AWS technologies to utilize block-level and incremental snapshots and this is the most efficient and potent form of backup available for AWS.
- With the N2WS solutions, 100% of uptime and availablity is assured. 
- Adherence to specific government and compliance requirements for the AWS Cloud. As Cloud Protection Manager (CPM) integrates coherently, AWS security standards of backups are meant.
- Cross-region and cross-account DR. Ability to move data between  regions with 247 access.



**How is N2WS Deployed**

- Can be found in the AWS market place (This is distributed as an AMI on AWS) 



**N2WS Editions and prices**

- 1. Cloud Protection Manager Free Trial & BYOL Edition 
This includes bring your N2WS linces and also AWS usage fees apply
- 2. Cloud Protection Manager Standard Edition
This costs $199.00 per month for software plus AWS usage fees
- 3. Cloud Protection Manager Free Edition
Costs $0.00 per hour for the N2WS software plus AWS usage fees (Note: The maximum backup here is five (5) instance.) 
- 4. Cloud Protection Manager Advanced Edition
This cost $399.00 per month for software plus AWS usage fees and this supports 10 users and 10 AWS accounts
- 5. Cloud Protection Manager Enterprise Edition
This cost $399.00 per month for software plus AWS usage fees and supports upto 20 users and 20 AWS accounts


**Note:** They are all free ties eligible to


**Links**

[https://www.veeam.com/aws-backup-solutions.html](https://www.veeam.com/aws-backup-solutions.html)
[https://n2ws.com/product](https://n2ws.com/product)
[https://stackoverflow.com/questions/18650697/cost-of-storing-ami?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa](https://stackoverflow.com/questions/18650697/cost-of-storing-ami?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa) 
[https://www.theregister.co.uk/2018/01/16/veeam_buys_aws_ec2_instance_backup_and_recovery_biz/](https://www.theregister.co.uk/2018/01/16/veeam_buys_aws_ec2_instance_backup_and_recovery_biz/)
[https://www.zdnet.com/article/veeam-invests-in-aws-disaster-recovery-with-42-5m-n2ws-acquisition/ ](https://www.zdnet.com/article/veeam-invests-in-aws-disaster-recovery-with-42-5m-n2ws-acquisition/ )