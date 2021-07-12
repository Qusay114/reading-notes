# One-to-One Relationship

Define the data models : 

        @Entity
        public class Library {

            @Id
            @GeneratedValue
            private long id;

            @Column
            private String name;

            @OneToOne
            @JoinColumn(name = "address_id")
            @RestResource(path = "libraryAddress", rel="address")
            private Address address;
            
            // standard constructor, getters, setters
        }
        @Entity
        public class Address {

            @Id
            @GeneratedValue
            private long id;

            @Column(nullable = false)
            private String location;

            @OneToOne(mappedBy = "address")
            private Library library;

            // standard constructor, getters, setters
        }


To expose these entities as resources , we will create two repositories  :


        public interface LibraryRepository extends CrudRepository<Library, Long> {}
        public interface AddressRepository extends CrudRepository<Address, Long> {}


There are several types of database relationships. Today we are going to cover the following:

One to One Relationships
One to Many and Many to One Relationships
Many to Many Relationships
Self Referencing Relationships
When selecting data from multiple tables with relationships, we will be using the JOIN query.