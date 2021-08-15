# Room Library : 

The Room persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite. Room provides the following benefits:
1. Compile-time verification of SQL queries.
2. Convenience annotations that minimize repetitive and error-prone boilerplate code.
3. Streamlined database migration paths.

### Room Entity : 
we need entity(table) to model our data .

Example : 

                @Entity(tableName = "task_details")
                public class TaskDetails {

                    @PrimaryKey(autoGenerate = true)
                    private Long id ;

                    @ColumnInfo(name = "task_title")
                    private String title ;
                    @ColumnInfo(name = "task_description")
                    private String description ;

                    public TaskDetails(String title , String description){
                        this.title = title ;
                        this.description = description ;
                    }

                    public Long getId() {
                        return id;
                    }

                    public String getTitle() {
                        return title;
                    }

                    public String getDescription() {
                        return description;
                    }

                    public void setId(Long id) {
                        this.id = id;
                    }

                    public void setTitle(String title) {
                        this.title = title;
                    }

                    public void setDescription(String description) {
                        this.description = description;
                    }
                }


### Room Data access object : 

we need to create a class to get access to the database , and perform crud operations on it .

Example :

                @Dao
                public interface TaskDao {
                    @Insert
                    void insertOneTask(TaskDetails task) ;

                    @Query("SELECT * FROM task_details WHERE task_title LIKE :title")
                    TaskDetails findTaskByTitle(String title) ;

                    @Query("SELECT * FROM task_details")
                    List<TaskDetails> findAllTasks() ;

                    @Delete
                    void deleteTask(TaskDetails task) ;

                }


### Database :

finally we need a class to represent the database and wires everything else together : 

                @Database(entities = {TaskDetails.class} , version = 1)
                public abstract class TaskDatabase extends RoomDatabase {

                    public abstract TaskDao taskDao();
                }






![roomImage](https://i.stack.imgur.com/mYsKP.png)
