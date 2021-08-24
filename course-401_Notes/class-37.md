# Amazon S3 : 

Amazon S3 has a simple web services interface that you can use to store and retrieve any amount of data, at any time, from anywhere on the web. It gives any developer access to the same highly scalable, reliable, fast, and inexpensive data storage infrastructure that Amazon uses to run its own global network of web sites. The service aims to maximize benefits of scale and to pass those benefits on to developers.


### Advantages of using Amazon S3 :

* Creating buckets – Create and name a bucket that stores data. Buckets are the fundamental containers in Amazon S3 for data storage.

* Storing data – Store an infinite amount of data in a bucket. Upload as many objects as you like into an Amazon S3 bucket. Each object can contain up to 5 TB of data. Each object is stored and retrieved using a unique developer-assigned key.

* Downloading data – Download your data or enable others to do so. Download your data anytime you like, or allow others to do the same.

* Permissions – Grant or deny access to others who want to upload or download data into your Amazon S3 bucket. Grant upload and download permissions to three types of users. Authentication mechanisms can help keep data secure from unauthorized access.

* Standard interfaces – Use standards-based REST and SOAP interfaces designed to work with any internet-development toolkit.

### Bucket :

A bucket is a container for objects stored in Amazon S3. Every object is contained in a bucket.
Buckets serve several purposes:

* They organize the Amazon S3 namespace at the highest level.

* They identify the account responsible for storage and data transfer charges.

* They play a role in access control.

* They serve as the unit of aggregation for usage reporting.


### Objects : 

Objects are the fundamental entities stored in Amazon S3. Objects consist of object data and metadata. The data portion is opaque to Amazon S3. The metadata is a set of name-value pairs that describe the object. These include some default metadata, such as the date last modified, and standard HTTP metadata, such as Content-Type. You can also specify custom metadata at the time the object is stored , An object is uniquely identified within a bucket by a key (name) and a version ID.

### Keys :

A key is the unique identifier for an object within a bucket. Every object in a bucket has exactly one key. The combination of a bucket, key, and version ID uniquely identify each object. So you can think of Amazon S3 as a basic data map between "bucket + key + version" and the object itself. Every object in Amazon S3 can be uniquely addressed through the combination of the web service endpoint, bucket name, key, and optionally, a version.




<br><br><br><br>
<br><br><br><br>


![AmazonS3](https://blog.shikisoft.com/assets/images/post_imgs/s3-bucket-to-another-account.png)