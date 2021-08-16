# Serverless : 

Serverless is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers. A serverless application runs in stateless compute containers that are event-triggered, ephemeral (may last for one invocation), and fully managed by the cloud provider. Pricing is based on the number of executions rather than pre-purchased compute capacity, isn’t it the ideal framework for that project you have been planning since a long time? Well, go ahead do it.
Serverless applications are event-driven cloud-based systems where application development rely solely on a combination of third-party services, client-side logic and cloud-hosted remote procedure calls (Functions as a Service).
<br><br><br>
![serverless](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2018/07/23/serverelss-app-arch.png)
<br><br><br>
# AWS Amplify : 

AWS Amplify is a set of tools and services that can be used together or on their own, to help front-end web and mobile developers build scalable full stack applications, powered by AWS. With Amplify, you can configure app backends and connect your app in minutes, deploy static web apps in a few clicks, and easily manage app content outside the AWS console.

Amplify supports popular web frameworks including JavaScript, React, Angular, Vue, Next.js, and mobile platforms including Android, iOS, React Native, Ionic, Flutter. Get to market faster with AWS Amplify.

The Benefits : 

- Configure backends fast
- Seamlessly connect frontends
- Easily manage content
- Deploy in a few clicks


# GraphQL : 

The GraphQL Transform provides a simple to use abstraction that helps you quickly create backends for your web and mobile applications on AWS. With the GraphQL Transform, you define your application’s data model using the GraphQL Schema Definition Language (SDL) and the library handles converting your SDL definition into a set of fully descriptive AWS CloudFormation templates that implement your data model.

Example : 

        type Blog @model {
          id: ID!
          name: String!
          posts: [Post] @connection(name: "BlogPosts")
        }
        type Post @model {
          id: ID!
          title: String!
          blog: Blog @connection(name: "BlogPosts")
          comments: [Comment] @connection(name: "PostComments")
        }
        type Comment @model {
          id: ID!
          content: String
          post: Post @connection(name: "PostComments")
        }


<br><br><br><br>
![amazon-cloud](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2020/05/04/Offline1.png)