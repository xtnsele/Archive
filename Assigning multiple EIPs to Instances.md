**Assigning Multiple IPs' to an Instance**


Things to note before creating a assigning Multiple EIP to Instances.
- Classic EC2 instances can only have a single Elastic IP address associated (attached) to them. 
 
- To have multiple IP addresses associated with your instance. You must use VPC and setup multiple network interfaces on your instance.

**INFO:** AWS announced sometime between 2012 and 2014  that a single ENI can have multiple EIPs assigned to it. This answer, and the question, are no longer relevant as a result.



[https://aws.amazon.com/premiumsupport/knowledge-center/attach-second-eni-auto-scaling/](https://aws.amazon.com/premiumsupport/knowledge-center/attach-second-eni-auto-scaling/)

[https://www.internetstaff.com/multiple-ec2-network-interfaces-on-red-hat-centos-7/](https://www.internetstaff.com/multiple-ec2-network-interfaces-on-red-hat-centos-7/)
