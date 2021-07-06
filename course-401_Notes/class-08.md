# Solid principles : 
solid which stands for the first letters of each principle , it is about how to design your code which gurantees avoiding code smells , refactoring code , and Agile or Adaptive software development .
 
1. Single responsiblity principle : 
this princple is  about giving each class one functionallity . 
Example: 

          public class Car(){
          public String price ;
          public String color
          public Car(String price , String color){
          this.price = price ;
          this.color = color;
            }
          }
 

 
          public class Output(){
            public Car car ;
          public Output(Car car){
            this.car = car ;
            }
          public String getData(){
            return "price: " + this.car.price + " , color: " +this.car.color ;
            }
          }


2. Open-Closed Principle : 
this means your class should be close for modifiction and open for extension .


3. Liskov Substitution Principle :
this means that the child classes should be substitable for the thir parent class .


4. Interface Segregation Principle :
This means the interfaces should be only if needed .


5. Dependency Inversion Principle : 
this means that high level modules should not depend on low level modules; both should depend on abstractions. Abstractions should not depend on details. Details should depend upon abstractions.


