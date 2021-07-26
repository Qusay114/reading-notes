# Spring Boot and OAuth2 :

### Steps to use OAuth2 in your project : 

* create your project using spring intializer and add web dependency .
to do that in the terminal use this command : 

        $ mkdir ui && cd ui
        $ curl https://start.spring.io/starter.tgz -d style=web -d name=simple | tar -xzvf -

* add a home page to your project and style it if you want .

* to secure your application with Github and spring security : 


        <dependency>
          <groupId>org.springframework.boot</groupId>
          <artifactId>spring-boot-starter-oauth2-client</artifactId>
        </dependency>


this will secure your app with OAuth 2.0 by default .

* To use GitHub’s OAuth 2.0 authentication system for login, you must first Add a new GitHub app :

Select "New OAuth App" and then the "Register a new OAuth application" page is presented. Enter an app name and description. Then, enter your app’s home page, which should be http://localhost:8080, in this case. Finally, indicate the Authorization callback URL as http://localhost:8080/login/oauth2/code/github and click Register Application.


Configure application.yml
Then, to make the link to GitHub, add the following to your application.yml:

        application.yml
        spring:
          security:
            oauth2:
              client:
                registration:
                  github:
                    clientId: github-client-id
                    clientSecret: github-client-secret


Simply use the OAuth 2.0 credentials you just created with GitHub, replacing github-client-id with the client id and github-client-secret with the client secret.




