# AppExecutors

This will allow to execute queries to Room Database without using the main thread. 

## Example: 


        AppExecutors.getInstance().diskIO().execute(new Runnable () {

            @Override
            public void run() {
             // Your Dao queries go here
              
            }
        });
        

## Example 2:  Queries that need to update main ui : 


        AppExecutors.getInstance().diskIO().execute(new Runnable () {

            @Override
            public void run() {
              // Dao queries go here
              
              // allow to run on UiThread
                 runOnUiThread(new Runnable() {
                     @Override
                     public void run() {
                             /*
                             * Your UI logic goes here
                             */
                     }
                 });
            }
        });
        
