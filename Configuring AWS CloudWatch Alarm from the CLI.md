
**Configuring AWS CloudWatch Alarm from the CLI for a Single Instance**

**Prerequisite**

First ensure the AWS commandlets are installed

On Windows

    PS C:\> Install-Module -Name AWSPowerShell

   `PS C:\> Install-Module -Scope CurrentUser -Name AWSPowerShell.NetCore -Force`

[https://docs.aws.amazon.com/powershell/latest/userguide/pstools-getting-set-up-windows.html](https://docs.aws.amazon.com/powershell/latest/userguide/pstools-getting-set-up-windows.html)

**Solution For a Single EC2 Instance, "Apply CloudWatch Alarm"**

Run this syntax from the PowerShell to run this against a single instance in each region by changing the instance type and region respectively.

Ensure you have AWS CLI configured on your local PC and set to the desired region you want to implement CloudWatch on the instance.

    aws cloudwatch put-metric-alarm  --alarm-name "i-xxxxxxxxxe9-SystemCheck" --namespace AWS/EC2 --metric-name StatusCheckFailed_System --dimensions "Name=InstanceId , Value=i-xxxxxxxxxe9" --alarm-description "autorecoveryfor-i-xxxxxxxxxe9"
      --alarm-actions "arn:aws:automate:eu-central-1:ec2:recover" "arn:aws:sns:eu-central-1:enterAccountID:AlarmStatusCheckFailedSystem" --statistic Maximum --period 60 --evaluation-periods 2 --threshold 1 --comparison-operator GreaterThanOrEqualToThreshold --treat-missing-data missing --unit Count

**Note**:
Enter these information in the script above and below correctly depending on your usecase.

- enterAccountID 
- Instance ID "i-xxxxxxxxxe9" should be entered corrected.



**Solution to apply all EC2 Instances in all Regions, "Apply CloudWatch Alarm"**

Use the script below

    # loop through all regions
    $region=Get-AWSRegion
    foreach ($reg in $region)
    {
    $tempregion=$reg.Region
    # set the default region you will work on to current region in the loop
    aws configure set default.region $tempregion
    # Create SNS topic for the current region
    aws sns create-topic --name AlarmStatusCheckFailedSystem
    aws sns subscribe --topic-arn arn:aws:sns:"$tempregion":enterAccountID:AlarmStatusCheckFailedSystem --protocol email --notification-endpoint training@test.com
    # loop through all Instanced in current region
    $Instances= aws ec2 describe-instances --query 'Reservations[*].Instances[*].[Placement.AvailabilityZone, State.Name, InstanceId]' --output text |%{if ($_.split("`t")[0] -match "$tempregion") { $_.split("`t")[2]; } }
      foreach ($Instance in $Instances)
      {
      $tempinstance=$Instance
    # set alarm for the metric StatusCheckFailed_System with auto recovery option for current Instance
    $arn2="arn:aws:sns:"+$tempregion+":enterAccountID:AlarmStatusCheckFailedSystem"
    $arn1="arn:aws:automate:"+$tempregion+":ec2:recover"
    aws cloudwatch put-metric-alarm  --alarm-name "$tempinstance-SystemCheck" --namespace AWS/EC2 --metric-name StatusCheckFailed_System --dimensions "Name=InstanceId , Value=$tempinstance" --alarm-description "autorecoveryfori-$tempinstance" --alarm-actions $arn1 $arn2 --statistic Maximum --period 60 --evaluation-periods 2 --threshold 1 --comparison-operator GreaterThanOrEqualToThreshold --treat-missing-data missing --unit Count
      } 
    }


Note, the following that needs to be changed in the script above

- enterAccountID
- Email-ID (endpoint) training@test.com