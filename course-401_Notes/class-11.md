# Spring : 
The Spring Framework (Spring) is an open-source application framework that provides infrastructure support for developing Java applications. One of the most popular Java Enterprise Edition (Java EE) frameworks, Spring helps developers create high performing applications using plain old Java objects (POJOs).
<br><br><br>
![spring](https://docs.spring.io/spring-framework/docs/3.2.x/spring-framework-reference/html/images/spring-overview.png)

### Create a Web Controller :
we can identify the controller by the @Controller annotation . 
in the following example , we will create a GreetingController , with /greeting end point to handle get requests : 

        package com.example.servingwebcontent;

        import org.springframework.stereotype.Controller;
        import org.springframework.ui.Model;
        import org.springframework.web.bind.annotation.GetMapping;
        import org.springframework.web.bind.annotation.RequestParam;

        @Controller
        public class GreetingController {

          @GetMapping("/greeting")
          public String greeting(@RequestParam(name="name", required=false, defaultValue="World") String name, Model model) {
            model.addAttribute("name", name);
            return "greeting";
          }

        }


here in the example we connect any get request to the /greeting endpoint , to greeting method


### Add a Home Page :

Static resources, including HTML and JavaScript and CSS, can be served from your Spring Boot application by dropping them into the right place in the source code. By default, Spring Boot serves static content from resources in the classpath at /static (or /public). The index.html resource is special because, if it exists, it is used as a "`welcome page,"serving-web-content/ which means it is served up as the root resource (that is, at `http://localhost:8080/). As a result, you need to create the following file (which you can find in src/main/resources/static/index.html)  : 

        <!DOCTYPE HTML>
        <html>
        <head> 
            <title>Getting Started: Serving Web Content</title> 
            <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
        </head>
        <body>
            <p>Get your greeting <a href="/greeting">here</a></p>
        </body>
        </html>






