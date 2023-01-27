# streaming-02-multiple-processes

> Multiple processes accessing a shared resource concurrently

This example starts up a shared database and three different processes that represent multiple users, or locations, or programs hitting a shared database at the same time. 

## About

Execute about.py to generate some useful information.

## First Run

Executing multiple_processes.py script.

Read the output. Read the code. 
Try to figure out what's going on. 

1. What libraries did we import?
    ##### We imported SQLite 3, time, multiprocessing, os, datetime, platform, and sys
2. Where do we set the task_duration?
    ##### The task duration is right after we import the libraries. This is where we define our variables.
3. How many functions are defined? 
    ##### 7
4. What are the function names?
    ##### 1: Create table. 2: Drop Table. 3: Define the process. 4: Process one. 5: Process two. 6: Process three. 7: Recreate the database.    
5. In general, what does each function do? 
    ##### 1: Getting the environment ready to create our pets table. Creating a connection, creating a SQL statement, defining the excution 
    ##### 2: Drop table gets rid of the table, but in this instance we are using it to ensure we don't have duplicate pets
    ##### 3: Defining the process for inserting the pets to make entering the data easier.
    ##### 4 - 6: Enter the actual pet data.
    ##### 7: Creating a clean version of our pets table
6. Where does the execution begin?
    ##### At the bottom of the file
7. How many processes do we start?
    ##### There are 3 processes
8. How many records does each process insert?
    ##### There are 2 records for each process (6 total records)

In each case, the process gets a connection to the database, and a cursor to execute SQL statements. They insert a record, and get out of the database quickly.

In general, we're successful and six new records get inserted. 

## Second Run

For the second run, we modify the task_duration to make each task take 3 seconds. Run it again. 

With the longer tasks, we now get into trouble:
    one process will have the database open and be working on it then when another process tries to do the same, it can't and we end up with an error. 

To document results, clear the terminal, run the script, and paste all of the terminal contents into the output file.

Use out0.txt to document the first run. 

Use out3.txt to document the second run.

## Learn More

Check out Wikipedia's article on deadlock and other sources to learn how to prevent and avoid locking issues in concurrent processes. 
