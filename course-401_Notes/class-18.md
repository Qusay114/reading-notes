# ManyToMany Relationship : 

in this kind of relation , both of the entity will have many of the other entity , 
and example on that : the relation between Student and Subject , will be many to many where the student can have many subjects , and the subject can have many students .

### The Model Classes : 

in the model class , we should create @ManyToMany notation and a join table and the list 

Example :

        @Entity
        @Table(name = "Employee")
        public class Employee { 
            // ...
        
            @ManyToMany(cascade = { CascadeType.ALL })
            @JoinTable(
                name = "Employee_Project", 
                joinColumns = { @JoinColumn(name = "employee_id") }, 
                inverseJoinColumns = { @JoinColumn(name = "project_id") }
            )
            Set<Project> projects = new HashSet<>();
          
            // standard constructor/getters/setters
        }



        @Entity
        @Table(name = "Project")
        public class Project {    
            // ...  
        
            @ManyToMany(mappedBy = "projects")
            private Set<Employee> employees = new HashSet<>();
            
            // standard constructors/getters/setters   
        }


![image](https://www.baeldung.com/wp-content/uploads/2017/09/New.png)


