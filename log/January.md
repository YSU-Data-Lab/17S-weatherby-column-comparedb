Prior to the below dates I was taking in documentation based on MySQL, MonetDB, I briefly looked at Cassandra and want to compare benchmarks to all three. I believe that my benchmarking will be much fairer since all programs will be running from memory. Memory hierarchy played an important role in benchmarking and I am correcting this variable so it is the same across the board thus comparing only the benchmarks of the databases.

Result deadline: **March 7, 2017**

**January 17, 2017**

**3:00 PM** Becoming familiar with terminal and the Ubuntu server environment. Trying to upload some kind of file or documentation to GitHub.

**3:00 PM** Still fiddling with the terminal environment. It is getting easier to navigate, though I am not sure how to view or use programs yet. This has shown me really how much I take my GUI for granted.
Dr. Yu has provided me with commands to get into the MySQL (Server?) for now. I will start with this and attempt to run trials there first. After the MySQL trials are complete, I will then be concerned about getting MonetDB working.

**3:30 PM** Learned how to make files and folders within GitHub.com. Spent a lot of time googling documentation on terminal.

**4:30 PM** Still working with the terminal window and trying to generate my own random data. It hasn't been going very well. All it seems to do it throw out an output file that I have no clue how to read. Attempted to copy and play with Aikins directory so I wouldn't damage the original contents in case I needed to reference them again.

**January 24, 2017**

**12:00 PM to 2:30 PM** Today I worked on trying to generate data. I ran into some difficulty for a few reasons: One being unfamiliality with Ubunutu. I didn't realize that I was to be typing a very specific command "./dbgen -s 1" into the directory where dbgen was sitting. I've just been trying to issue the command "dbgen -s" which only results in a strange file named "output.ldif" after working past this complication I attempted to re-familiarize myself with MySQL only to run into trouble when trying to issue the command "create database tpch_memory" and I am attempting to follow up on this. I am not meeting my intended personal progress on this project and plan to work more on it Thursday this week.

Other notes: Moved all ".tbl" files to my directory under "~weatherby/testdata" I anticipate to test 1GB against memory in MySQL and MonetDB. Larger sets of data should be easier to distinguish a proper benchmark.
Commands to remember: SET default_storage_engine=MEMORY;

**January 26, 2017**

**1:30 PM to 3:00 PM** Today I have learned how to import data to MySQL from the .TBL files. I have written all the script and laid it out in a text file on the main branch of this repository. I am running into this issues with this now:

mysql> LOAD DATA LOCAL INFILE 'lineitem.tbl' INTO TABLE lineitem FIELDS TERMINATED BY '|';

ERROR 1114 (HY000): The table 'lineitem' is full

Will discuss Tuesday about what I'm running into here and how to remedy it. I have tried scaling down the filesizes, but even Aikin's 100m project is too large for this particular table. We are using the memory engine, so maybe that has something to do with it. Tried 1GB, 500MB, 250MB, 200MB, 100MB - I need a fairly sizable project in order to properly benchmark, don't I?

**January 27, 2017**

**12:15 PM to 1:00 PM** Remedied issue with MySQL and the memory engine limitation with the following commands:

SET GLOBAL tmp_table_size = 1024 * 1024 * 1024 * 2;
SET GLOBAL max_heap_table_size = 1024 * 1024 * 1024 * 2;
If you are checking the above variables with

SELECT @@max_heap_table_size;
or
SHOW VARIABLES LIKE 'max_heap_table_size';

Also looked at the queries with qgen for testing within the ~/tpch/dbgen/queries/ directory. Plan to have entire benchmark on 750MB of data by the end of January and then begin next step with MonetDB and Cassandra.

Attempted proper benchmarking, unsure about results: Opened Issue #2 Memory == MYISAM Performance

**January 28, 2017**

Solved Issue: Memory database and MYISAM seemed to be running at equivalent times. Found that the table setups were missing Primary and Foreign Keys when testing against the queries. The addition of the keys have improved the performance drastically and benchmarks now run as expected.

This was the final hurdle of the first phase of my project.

**January 30, 2017**

Double checked everything with MySQL to make sure I was running the benchmarks properly. Everything for the MySQL side looks good to go. Inadvertendly when testing if the memory engine was working I did end up with MYISAM benchmarks as well. They were simple enough to perform. I believe that with missing Primary and Foriegn Keys that Aikin's project is largely invalid. The times in MySQL for Aikins were pretty long just for 100MB of data. My queries were ran using 1GB of data and ran under ten seconds for the MYISAM engine and half that for Memory engine. I think it's safe to say that the original benchmark is not at all accurate.

The mistake: I made the mistake of looking at Aikins table schema instead of referring to the official documentation at first. I was pretty confused as to why the times were so long when I knew that the benchmarks should provide me a reasonable time. Originally, just for Aikins Query 1, I calculated that it would take 30 seconds for the initial 100MB of data multiplied by 5 for every +100MB of data or (30)x(5)^(n-1) where n is every 100MB of data, and I got this based on the results of 3 queries at 100MB, 200MB and 300MB. 

Benchmark data saved accordingly.

**End of Log File**
