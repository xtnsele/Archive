**Modifying an EBS Volume from the Console**

Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.

Copy the instance ID

Navigate to Volumes, select the volume to modify(by searching for the instance ID if there are a lot), 

Choose Actions, Modify Volume to the size you desire.

Now follow the prompts to complete extending the drive and finish

**Step 2:**

Navigate to the linux Command Prompt

Modifying volume size has no practical effect until you also extend the volume's file system to make use of the new storage capacity. 

Note: Use the existing file System to show the existing hard disk space onn your instance

Commands:
[ec2-user ~]$dh -f
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvda1            8.0G  943M  6.9G  12% /

or

To list the block devices attached to your instance
[ec2-user ~]$lsblk

For ext2, ext3, and ext4 file systems,
--->
[ec2-user ~]$resize2fs /dev/xvdf1


For XFS file systems
[ec2-user ~]$xfs_growfs -d /mnt


My Scenario
- To fix increase the file system of xvda1
[ec2-user ~]$growpart /dev/xvda1

The result would be as shown below
CHANGED: disk=/dev/xvda partition=1: start=4096 old: size=16773086,end=16777182 new: size=73396190,end=73400286

Now use the command below to see if it has taken effect
[ec2-user ~]$ lsblk

Note: with the command dh -f
It might show the previous available space. Simply reboot or initialize it [3]



[1] [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/console-modify.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/console-modify.html)

[2] [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html)

[3] [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-initialize.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-initialize.html)