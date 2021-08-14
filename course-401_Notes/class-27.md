# Android Activity : 
it's where we put our data into it , the activity usally consists a layout to put our design (user interface) such as buttons , texts , images and ..etc  , and class that will hold the functionality for the activity .

example : 

the class : 

                public class TasksActivity extends AppCompatActivity {

                    @Override
                    protected void onCreate(Bundle savedInstanceState) {
                        super.onCreate(savedInstanceState);
                        setContentView(R.layout.activity_tasks);

                        RecyclerView recyclerView = findViewById(R.id.recycleViewList);

                        String lorem = "Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, \n" +
                                "        totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. \n" +
                                "        Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, \n" +
                                "        sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt." ;

                        List<TaskDetails> tasks = new ArrayList<>();
                        tasks.add(new TaskDetails("Task 1" , lorem));
                        tasks.add(new TaskDetails("Task 2" , lorem));
                        tasks.add(new TaskDetails("Task 3" , lorem));
                        tasks.add(new TaskDetails("Task 4" , lorem));
                        tasks.add(new TaskDetails("Task 5" , lorem));
                        tasks.add(new TaskDetails("Task 6" , lorem));
                        tasks.add(new TaskDetails("Task 7" , lorem));
                        tasks.add(new TaskDetails("Task 8" , lorem));


                        TaskAdapter taskAdapter = new TaskAdapter(tasks) ;

                        LinearLayoutManager linearLayoutManager = new LinearLayoutManager(
                                this ,
                                LinearLayoutManager.VERTICAL ,
                                false) ;

                        recyclerView.setLayoutManager(linearLayoutManager);
                        recyclerView.setAdapter(taskAdapter);

                    }
                }


The Layout of the activity : 

  
                <?xml version="1.0" encoding="utf-8"?>
                <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
                    xmlns:app="http://schemas.android.com/apk/res-auto"
                    xmlns:tools="http://schemas.android.com/tools"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    tools:context=".tasks.TasksActivity">
                    
                <androidx.recyclerview.widget.RecyclerView
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:id="@+id/recycleViewList"
                    />

                </androidx.constraintlayout.widget.ConstraintLayout>


# Intents : 

we use the intents usually to start an activity from another one , and we can pass data throw it using putExtra . 

Example :

                Intent allTasksIntent = new Intent(getApplicationContext() , AllTasksActivity.class);
                startActivity(allTasksIntent);


# SharedPrefrences : 

we use sharedprefrennces to save our data (such as the local storage) and we can pull the data from it .

Example :

                SharedPreferences sharedPreferences = PreferenceManager.getDefaultSharedPreferences(this);
                SharedPreferences.Editor preferenceEditor =  sharedPreferences.edit();
                String username = usernameEditText.getText().toString();
                preferenceEditor.putString("username" , username);
                preferenceEditor.apply();
