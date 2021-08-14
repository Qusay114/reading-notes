# RecyclerViews : 

RecyclerView is the ViewGroup that contains the views corresponding to our data. It's a view itself, so we add RecyclerView into our layout the way you would add any other UI element.
The RecyclerView requests those views, and binds the views to their data, by calling methods in the adapter , and this adapter we will create it . 

example on a created adapter : 

                public class TaskAdapter extends RecyclerView.Adapter<TaskAdapter.ViewHolder>{
                    private List<TaskDetails> taskDetailsList ;

                    public TaskAdapter(List<TaskDetails> taskDetailsList){
                        this.taskDetailsList = taskDetailsList ;
                    }

                    @NonNull
                    @Override
                    public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
                        View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.task_card_layout , parent , false);
                        return new ViewHolder(view);
                    }

                    @Override
                    public void onBindViewHolder(@NonNull TaskAdapter.ViewHolder holder, int position) {
                        TaskDetails taskDetails = taskDetailsList.get(position);
                        holder.taskTitle.setText(taskDetails.getTitle());
                        holder.taskDetails.setText(taskDetails.getDescription());

                    }



                    @Override
                    public int getItemCount() {
                        return this.taskDetailsList.size();
                    }

                    static class ViewHolder extends RecyclerView.ViewHolder{
                        private TextView taskTitle ;
                        private TextView taskDetails ;

                        public ViewHolder(@NonNull View itemView) {
                            super(itemView);
                            taskTitle  = itemView.findViewById(R.id.textViewTaskTitle);
                            taskDetails = itemView.findViewById(R.id.textViewTaskDetails) ;
                        }
                    }
                }


Example on the layouts : 

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


The CardView : 

                ?xml version="1.0" encoding="utf-8"?>
                <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
                    xmlns:tools="http://schemas.android.com/tools"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    xmlns:app="http://schemas.android.com/apk/res-auto">

                    <TextView
                        android:id="@+id/textViewTaskTitle"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="@string/task_1"
                        app:layout_constraintLeft_toLeftOf="parent"
                        app:layout_constraintRight_toRightOf="parent"
                        tools:layout_editor_absoluteY="37dp"
                        tools:ignore="MissingConstraints" />

                    <TextView
                        android:id="@+id/textViewTaskDetails"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="32dp"
                        android:text="@string/lorem"
                        app:layout_constraintHorizontal_bias="0.0"
                        app:layout_constraintLeft_toLeftOf="parent"
                        app:layout_constraintRight_toRightOf="parent"
                        app:layout_constraintTop_toBottomOf="@id/textViewTaskTitle" />


                </androidx.constraintlayout.widget.ConstraintLayout>
