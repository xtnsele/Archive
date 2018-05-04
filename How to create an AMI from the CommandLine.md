**How to create an AMI from the CommandLine**

Here is how you can create an AMI from an instance from the command line. 

AMI: Amazon Machine Images (AMI). An Amazon Machine Image (AMI) provides the information required to launch an instance, which is a virtual server in the cloud. You must specify a source AMI when you launch an instance. You can launch multiple instances from a single AMI when you need multiple 

**How to** 

aws ec2 create-image --instance-id i-0xxxxxxxxxxxxb --name "FrankfurtChrisinstance" --no-reboot 