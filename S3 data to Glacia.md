**Archiving Amazon S3 Data to Amazon Glacier**

**Things to consider** 
- Usecase to move S3 files to Glacier using object lifecycle management after a long period of time (CapEx reduced).

**Note:** Glacier is really meant for long term storage, which is very infrequently accessed. 
- It can also get very expensive to retrieve a large portion of your data in one go, as it's not meant for point-in-time restoration of lots of data (percentage wise).

If you archive objects using the Glacier storage option, you must inspect the storage class of an object before you attempt to retrieve it. The customary GET request will work as expected if the object is stored in S3 Standard or Reduced Redundancy (RRS) storage. It will fail (with a 403 error) if the object is archived in Glacier. In this case, you must use the RESTORE operation (described below) to make your data available in S3.

S3 was designed for for rapid retrival and we have seen this usecase several times, where we would go and pull customer data over a long period of time. 

[https://aws.amazon.com/blogs/aws/archive-s3-to-glacier/](https://aws.amazon.com/blogs/aws/archive-s3-to-glacier/ )  
