**Why I cannot access EC2 instance public IP from inside of instance itself?**

Here is an example, I have an Linux instance , say, private IP is 10.10.10.10, public IP is 54.54.54.54.

- Inside the instance, I could successfully ping it's private IP(10.10.10.10) and localhost. However, I cannot access it's public IP(54.54.54.54).

**Soulution**

Simply added the EIP of the instance to allow echoo reply and request tot the Public IP