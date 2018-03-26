Creating an AMI from the CLI

aws ec2 create-image --instance-id i-0b09a25c58929de26 --name "My server" --no-reboot


--no-reboot | --reboot (boolean)

By default, Amazon EC2 attempts to shut down and reboot the instance before creating the image. If the 'No Reboot' option is set, Amazon EC2 doesn't shut down the instance before creating the image. When this option is used, file system integrity on the created image can't be guaranteed.



https://docs.aws.amazon.com/cli/latest/reference/ec2/create-image.html