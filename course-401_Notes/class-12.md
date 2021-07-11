# RequestMapping Basics : 

### @RequestMapping-by path : 

Example : 

        @RequestMapping(value = "/ex/foos", method = RequestMethod.GET)
        @ResponseBody
        public String getFoosBySimplePath() {
            return "Get some Foos";
        }



### @RequestMapping - the HTTP method : 

Example : 

        @RequestMapping(value = "/ex/foos", method = POST)
        @ResponseBody
        public String postFoos() {
            return "Post some Foos";
        }




# RequestMapping and HTTP Headers : 

### @RequestMapping With the headers Attribute : 

we can shrink the mapping more by specifying a header for the request

Example : 

        @RequestMapping(value = "/ex/foos", headers = "key=val", method = GET)
        @ResponseBody
        public String getFoosWithHeader() {
            return "Get some Foos with Header";
        }

we can also add multiple headers using headers attribute of @RequestMapping : 

Example :

        @RequestMapping(
          value = "/ex/foos", 
          headers = { "key1=val1", "key2=val2" }, method = GET)
        @ResponseBody
        public String getFoosWithHeaders() {
            return "Get some Foos with Header";
        }


# RequestMapping With Path Variables :

### Single @PathVariable :

Example on a single path variable : 

        @RequestMapping(value = "/ex/foos/{id}", method = GET)
        @ResponseBody
        public String getFoosBySimplePathWithPathVariable(
          @PathVariable("id") long id) {
            return "Get a specific Foo with id=" + id;
        }


### Multiple @PathVariable :

Example : 

        @RequestMapping(value = "/ex/foos/{fooid}/bar/{barid}", method = GET)
        @ResponseBody
        public String getFoosBySimplePathWithPathVariables
          (@PathVariable long fooid, @PathVariable long barid) {
            return "Get a specific Bar with id=" + barid + 
              " from a Foo with id=" + fooid;
        }


# Accessing Data with JPA :
### using @Entity : 

Example :

        package com.example.accessingdatajpa;

        import javax.persistence.Entity;
        import javax.persistence.GeneratedValue;
        import javax.persistence.GenerationType;
        import javax.persistence.Id;

        @Entity
        public class Customer {

          @Id
          @GeneratedValue(strategy=GenerationType.AUTO)
          private Long id;
          private String firstName;
          private String lastName;

          protected Customer() {}

          public Customer(String firstName, String lastName) {
            this.firstName = firstName;
            this.lastName = lastName;
          }

          @Override
          public String toString() {
            return String.format(
                "Customer[id=%d, firstName='%s', lastName='%s']",
                id, firstName, lastName);
          }

          public Long getId() {
            return id;
          }

          public String getFirstName() {
            return firstName;
          }

          public String getLastName() {
            return lastName;
          }
        }

<br><br><br>
![image](https://terasolunaorg.github.io/guideline/5.2.0.RELEASE/en/_images/dataaccess_jpa_mapping.png)