# WebSockets : 

in this reading , it builds a server that accepts a message that carries a user'name.In response, the server will push a greeting into a queue to which the client is subscribed.


### Step 1 : set up your project : 

here is the pom.xml file : 

        <?xml version="1.0" encoding="UTF-8"?>
        <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
          <modelVersion>4.0.0</modelVersion>
          <parent>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-parent</artifactId>
            <version>2.5.2</version>
            <relativePath/> <!-- lookup parent from repository -->
          </parent>
          <groupId>com.example</groupId>
          <artifactId>messaging-stomp-websocket-initial</artifactId>
          <version>0.0.1-SNAPSHOT</version>
          <name>messaging-stomp-websocket-initial</name>
          <description>Demo project for Spring Boot</description>
          <properties>
            <java.version>1.8</java.version>
          </properties>
          <dependencies>
            <dependency>
              <groupId>org.springframework.boot</groupId>
              <artifactId>spring-boot-starter-websocket</artifactId>
            </dependency>

            <dependency>
              <groupId>org.springframework.boot</groupId>
              <artifactId>spring-boot-starter-test</artifactId>
              <scope>test</scope>
            </dependency>
          </dependencies>

          <build>
            <plugins>
              <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
              </plugin>
            </plugins>
          </build>

        </project>



and here is the build.gradle file :

        plugins {
          id 'org.springframework.boot' version '2.5.2'
          id 'io.spring.dependency-management' version '1.0.11.RELEASE'
          id 'java'
        }

        group = 'com.example'
        version = '0.0.1-SNAPSHOT'
        sourceCompatibility = '1.8'

        repositories {
          mavenCentral()
        }

        dependencies {
          implementation 'org.springframework.boot:spring-boot-starter-websocket'
          testImplementation 'org.springframework.boot:spring-boot-starter-test'
        }

        test {
          useJUnitPlatform()
        }


### step 2 : Create the models  : 

        public class HelloMessage {

          private String name;

          public HelloMessage() {
          }

          public HelloMessage(String name) {
            this.name = name;
          }

          public String getName() {
            return name;
          }

          public void setName(String name) {
            this.name = name;
          }
        }


        Greeting Model : 

        public class Greeting {

          private String content;

          public Greeting() {
          }

          public Greeting(String content) {
            this.content = content;
          }

          public String getContent() {
            return content;
          }

        }



### step 3 : Create the controller handling : 

        @Controller
        public class GreetingController {


          @MessageMapping("/hello")
          @SendTo("/topic/greetings")
          public Greeting greeting(HelloMessage message) throws Exception {
            Thread.sleep(1000); // simulated delay
            return new Greeting("Hello, " + HtmlUtils.htmlEscape(message.getName()) + "!");
          }

        }



### step 4 : Configure Spring for STOMP messaging : 

        import org.springframework.context.annotation.Configuration;
        import org.springframework.messaging.simp.config.MessageBrokerRegistry;
        import org.springframework.web.socket.config.annotation.EnableWebSocketMessageBroker;
        import org.springframework.web.socket.config.annotation.StompEndpointRegistry;
        import org.springframework.web.socket.config.annotation.WebSocketMessageBrokerConfigurer;

        @Configuration
        @EnableWebSocketMessageBroker
        public class WebSocketConfig implements WebSocketMessageBrokerConfigurer {

          @Override
          public void configureMessageBroker(MessageBrokerRegistry config) {
            config.enableSimpleBroker("/topic");
            config.setApplicationDestinationPrefixes("/app");
          }

          @Override
          public void registerStompEndpoints(StompEndpointRegistry registry) {
            registry.addEndpoint("/gs-guide-websocket").withSockJS();
          }

        }



### Step 5 : Create a Browser Client :

        <!DOCTYPE html>
        <html>
        <head>
            <title>Hello WebSocket</title>
            <link href="/webjars/bootstrap/css/bootstrap.min.css" rel="stylesheet">
            <link href="/main.css" rel="stylesheet">
            <script src="/webjars/jquery/jquery.min.js"></script>
            <script src="/webjars/sockjs-client/sockjs.min.js"></script>
            <script src="/webjars/stomp-websocket/stomp.min.js"></script>
            <script src="/app.js"></script>
        </head>
        <body>
        <noscript><h2 style="color: #ff0000">Seems your browser doesn't support Javascript! Websocket relies on Javascript being
            enabled. Please enable
            Javascript and reload this page!</h2></noscript>
        <div id="main-content" class="container">
            <div class="row">
                <div class="col-md-6">
                    <form class="form-inline">
                        <div class="form-group">
                            <label for="connect">WebSocket connection:</label>
                            <button id="connect" class="btn btn-default" type="submit">Connect</button>
                            <button id="disconnect" class="btn btn-default" type="submit" disabled="disabled">Disconnect
                            </button>
                        </div>
                    </form>
                </div>
                <div class="col-md-6">
                    <form class="form-inline">
                        <div class="form-group">
                            <label for="name">What is your name?</label>
                            <input type="text" id="name" class="form-control" placeholder="Your name here...">
                        </div>
                        <button id="send" class="btn btn-default" type="submit">Send</button>
                    </form>
                </div>
            </div>
            <div class="row">
                <div class="col-md-12">
                    <table id="conversation" class="table table-striped">
                        <thead>
                        <tr>
                            <th>Greetings</th>
                        </tr>
                        </thead>
                        <tbody id="greetings">
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
        </body>
        </html>



This HTML file imports the SockJS and STOMP javascript libraries that will be used to communicate with our server through STOMP over websocket. We also import app.js, which contains the logic of our client application. The following listing (from src/main/resources/static/app.js) shows that file: 


        var stompClient = null;

        function setConnected(connected) {
            $("#connect").prop("disabled", connected);
            $("#disconnect").prop("disabled", !connected);
            if (connected) {
                $("#conversation").show();
            }
            else {
                $("#conversation").hide();
            }
            $("#greetings").html("");
        }

        function connect() {
            var socket = new SockJS('/gs-guide-websocket');
            stompClient = Stomp.over(socket);
            stompClient.connect({}, function (frame) {
                setConnected(true);
                console.log('Connected: ' + frame);
                stompClient.subscribe('/topic/greetings', function (greeting) {
                    showGreeting(JSON.parse(greeting.body).content);
                });
            });
        }

        function disconnect() {
            if (stompClient !== null) {
                stompClient.disconnect();
            }
            setConnected(false);
            console.log("Disconnected");
        }

        function sendName() {
            stompClient.send("/app/hello", {}, JSON.stringify({'name': $("#name").val()}));
        }

        function showGreeting(message) {
            $("#greetings").append("<tr><td>" + message + "</td></tr>");
        }

        $(function () {
            $("form").on('submit', function (e) {
                e.preventDefault();
            });
            $( "#connect" ).click(function() { connect(); });
            $( "#disconnect" ).click(function() { disconnect(); });
            $( "#send" ).click(function() { sendName(); });
        });
