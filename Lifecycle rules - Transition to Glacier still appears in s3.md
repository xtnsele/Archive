**Lifecycle rules - Transition to Glacier still appears in s3**

- Even when you create a Zero (0) days lifecycle rule to move the entire bucket to Glacier.

**Explaination**

**Note:** If you use S3 for transitioning data to Glacier, you will not see data in Glacier service, the objects continue to reside in S3, but are stored using GLACIER storage class. You can look at the storage class of the object to confirm this.


**Recommended Solution**

- If you wish to have this seperation, we can manually download the s3 bucket, zip it and upload to Glacia Vault.
In this way we can have the the bucket (folders) uplaoded to Glacia Vault and deleted from S3.

**Note**: In this case, if we wish to recover any object, we would download and search for the object. 

[https://forums.aws.amazon.com/thread.jspa?threadID=111964](https://forums.aws.amazon.com/thread.jspa?threadID=111964) 