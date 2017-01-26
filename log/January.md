Prior to the below dates I was taking in documentation based on MySQL, MonetDB, I briefly looked at Cassandra and want to compare benchmarks to all three. I believe that my benchmarking will be much fairer since all programs will be running from memory. Memory hierarchy played an important role in benchmarking and I am correcting this variable so it is the same across the board thus comparing only the benchmarks of the databases.

Result deadline: **March 7, 2017**

**January 17, 2017**

**3:00 PM** Becoming familiar with terminal and the Ubuntu server environment. Trying to upload some kind of file or documentation to GitHub.

**3:00 PM** Still fiddling with the terminal environment. It is getting easier to navigate, though I am not sure how to view or use programs yet. This has shown me really how much I take my GUI for granted.
Dr. Yu has provided me with commands to get into the MySQL (Server?) for now. I will start with this and attempt to run trials there first. After the MySQL trials are complete, I will then be concerned about getting MonetDB working.

**3:30 PM** Learned how to make files and folders within GitHub.com. Spent a lot of time googling documentation on terminal.

**4:30 PM** Still working with the terminal window and trying to generate my own random data. It hasn't been going very well. All it seems to do it throw out an output file that I have no clue how to read. Attempted to copy and play with Aikins directory so I wouldn't damage the original contents in case I needed to reference them again.

**January 24, 2017**

**12:00 PM to 2:30 PM** Today I worked on trying to generate data. I ran into some difficulty for a few reasons: One being unfamiliality with Ubunutu. I didn't realize that I was to be typing a very specific command "./dbgen -s 1" into the directory where dbgen was sitting. I've just been trying to issue the command "dbgen -s" which only results in a strange file named "output.ldif" after working past this complication I attempted to re-familiarize myself with mySQL only to run into trouble when trying to issue the command "create database tpch_memory" and I am attempting to follow up on this. I am not meeting my intended personal progress on this project and plan to work more on it Thursday this week.

Other notes: Moved all ".tbl" files to my directory under "~weatherby/testdata" I anticipate to test 1GB against memory in mySQL and MonetDB. Larger sets of data should be easier to distinguish a proper benchmark.
Commands to remember: SET default_storage_engine=MEMORY;

**January 26, 2017**
**1:30 PM to 3:00 PM** Today I have learned how to import data to mySQL from the .TBL files. I have written all the script and laid it out in a text file on the main branch of this repository. I am running into this issues with this now:

mysql> LOAD DATA LOCAL INFILE 'lineitem.tbl' INTO TABLE lineitem FIELDS TERMINATED BY '|';
ERROR 1114 (HY000): The table 'lineitem' is full

Will discuss Tuesday about what I'm running into here and how to remedy it. I have tried scaling down the filesizes, but even Aikin's 100m project is too large for this particular table. We are using the memory engine, so maybe that has something to do with it. Tried 1GB, 500MB, 250MB, 200MB, 100MB - I need a fairly sizable project in order to properly benchmark, don't I?
