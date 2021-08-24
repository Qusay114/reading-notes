# Amazon SNS : 

Amazon Simple Notification Service (Amazon SNS) is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.

The A2A pub/sub functionality provides topics for high-throughput, push-based, many-to-many messaging between distributed systems, microservices, and event-driven serverless applications. Using Amazon SNS topics, your publisher systems can fanout messages to a large number of subscriber systems including Amazon SQS queues, AWS Lambda functions and HTTPS endpoints, for parallel processing, and Amazon Kinesis Data Firehose. The A2P functionality enables you to send messages to users at scale via SMS, mobile push, and email.

In some cases, your applications may require higher levels of security and need to be deployed into a private network. Some common cases for private networking and messaging include:

* Isolating development and testing environments
* Sharing personally identifiable information (PII) about your customers
* Hosting a PCI-compliant e-commerce website
* Developing healthcare applications subject to HIPAA
* Implementing a cryptographic algorithm subject to FIPS 140
* Processing mortgage applications in a banking system

By publishing messages privately from a private network, such as Amazon VirtualPrivate Cloud (VPC), you can improve the security of the traffic between your applications and Amazon SNS.

An Amazon Virtual Private Cloud (VPC) is a virtual network that closely resembles a traditional network that you’d operate in your own data center. Amazon VPC lets you provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. With VPC on AWS, you have little upfront investment, and you can scale your infrastructure in or out as necessary.


### Benefits and features

* Reliably deliver messages with durability

* Automatically scale your workload

* Keep messages private and secure

* Simplify your architecture with Message Filtering

Prerequisites

Step 1: Create a topic

Step 2: Create a subscription to the topic

Step 3: Publish a message to the topic

Step 4: Delete the subscription and topic

<br><br><br>

![AmazonSNS](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2017/11/20/introducing_sns_message_filtering_image_1.png)
