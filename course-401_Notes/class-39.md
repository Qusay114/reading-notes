# Amazon Kinesis:

Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information. Amazon Kinesis offers key capabilities to cost-effectively process streaming data at any scale, along with the flexibility to choose the tools that best suit the requirements of your application. With Amazon Kinesis, you can ingest real-time data such as video, audio, application logs, website clickstreams, and IoT telemetry data for machine learning, analytics, and other applications. Amazon Kinesis enables you to process and analyze data as it arrives and respond instantly instead of having to wait until all your data is collected before the processing can begin. 


### To set up Analytics Backend : 

run this commandss on CLI : 

        amplify add analytics


then you should push it : 

        amplify push 


### Add Analytics by adding these libraries into the dependencies block:

        dependencies {
            // Add these lines in `dependencies`
            implementation 'com.amplifyframework:aws-analytics-pinpoint:1.24.0'
            implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'
        }


<br><br><br>

![kinesis](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2017/02/01/implement_serverless_1.gif)

