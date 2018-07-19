AWS CLI Error "**All commands return Unknown**" output type: [None]

**Solution**

Often times the  **~/.aws/config** is having some configuration issues and needs to be reconfigured or modified. 

This is because there are multiple declarations for the same setting under a single role header. 

Therefore, editing the file manually will fix this issue.

See the link below on how to reconfigure AWS CLI or find the directory.

[https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)

**For Windows:**

    C:\Users\xxxxxxxxx\.aws
Here  you will find the config and credentials files.

Modify accordingly to the 

- AWS Access Key ID and Access 
- AWS Secret Access Key 