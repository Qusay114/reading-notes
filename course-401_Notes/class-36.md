To start, I want to clarify that "Amplify" is an umbrella term for multiple things. We have:
1. Amplify Libraries (UI/JS)
2. Amplify CLI (to create cloud-native applications)
3. Amplify Console (ci/cd and hosting for full-stack web apps)
4. Amplify Admin UI (UI to create and configure full-stack web apps)
You can check the homepage for more clarification - https://docs.amplify.aws/ (Links to an external site.)What is a serverless architecture?
When we create a website traditionally we build and deploy the web applications and we have control over the HTTP requests that are requested to our server. Our application runs on that server and we are responsible for provisioning and managing the resources for it. But there are some issues,

* To keep the server up we get charged even when we are not serving any requests
* We are responsible for server uptime and server maintenance and its resources
* Also responsible for implementing the proper security updates to the server
* When our usage scales up or scales down we need to manage to scale up or down our server
* In serverless architecture, we overcome these issues and it helps us achieve
* Low maintenance
* Low cost
* Scalability

AWS, Azure, or Google Cloud Platform are completely responsible for developing a piece of code by dynamically designating the resources. And the platform only charges for the number of resources used to run the code. The code sent to the cloud provider for execution is in the form of functions. Sometimes called “Functions as a Service ” or “FaaS”. We use AWS Lambda (Links to an external site.) to communicate with AWS cloud services.Register a user (Links to an external site.)
The default CLI flow as mentioned in the getting started guide (Links to an external site.) requires a username, password and a valid email id as parameters to register a user. Invoke the following api to initiate a sign up flow.


        AuthSignUpOptions options = AuthSignUpOptions.builder()
            .userAttribute(AuthUserAttributeKey.email(), "my@email.com")
            .build();
        Amplify.Auth.signUp("username", "Password123", options,
            result -> Log.i("AuthQuickStart", "Result: " + result.toString()),
            error -> Log.e("AuthQuickStart", "Sign up failed", error)
        );


The next step in the sign up flow is to confirm the user. A confirmation code will be sent to the email id provided during sign up. Enter the confirmation code received via email in the confirmSignUp call.


        Amplify.Auth.confirmSignUp(
            "username",
            "the code you received via email",
            result -> Log.i("AuthQuickstart", result.isSignUpComplete() ? "Confirm signUp succeeded" : "Confirm sign up not complete"),
            error -> Log.e("AuthQuickstart", error.toString())
        );


docs.amplify.awsdocs.amplify.aws
Amplify Framework Docs 
Amplify Framework documentation - Learn how to use Amplify to develop and deploy cloud-powered mobile and web apps.
Amazon Web Services, Inc.Amazon Web Services, Inc.
AWS Lambda – Serverless Compute - Amazon Web Services 
AWS Lambda lets you run code without provisioning or managing servers. You pay only for the compute time you consume.