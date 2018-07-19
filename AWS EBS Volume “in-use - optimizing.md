"AWS EBS Volume “in-use - optimizing”


**Things to know and solution**

The in-use - optimizing state relates to EBS volume resizing.

in-use indicates that this volume is attached to an EC2 instance.
optimizing is the volume's modification state.
According to the AWS documentation on volume modifications:

An EBS volume being modified goes through a sequence of states. After you issue a ModifyVolume directive, whether from the console, CLI, API, or SDK, the volume enters first the Modifying state, then the Optimizing state, and finally the Complete state.

[https://stackoverflow.com/questions/43771207/aws-ebs-volume-in-use-optimizing?rq=1](https://stackoverflow.com/questions/43771207/aws-ebs-volume-in-use-optimizing?rq=1) 

[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring_mods.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring_mods.html)