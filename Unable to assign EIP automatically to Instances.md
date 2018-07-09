**Unable to assign EIP automatically to Instances**

No Public IP is attached to EC2 instances when Launched or Recovered via N2WS Veeam CPM

**Answer**
-Instances running in a VPC will not get public IP addresses automatically. 

Therefore, if you wish to make them accessible from the internet, you will have to associate the instance with an Elastic IP address.