# MySQL and MonetDB Benchmarks
### An Overview

For my senior project, I took on the task of expanding a benchmark on several databases and their engines. My first task was tackling MySQL and getting the MYISAM and Memory engines out of the way. The second task was MonetDB. The third database, with time permitting, was to be Cassandra. Unfortunately, I was in the middle of the Cassandra benchmark when the cloud cut off. I did manage to get Cassandra installed though.


My project had some initial challenges. Firstly, I had to become acquainted with Ubuntu and terminal. Therefore, every action had to be performed through a command line interface. This was a daunting task, but I managed to pick up the command and syntax with ease. 


While benchmarking I discovered that the times were not matching the original project’s times. The original data was benchmarking much slower than the new data, and there was much more new data to process! Therefore, I began an investigation into the old benchmarking technique to see what the issue could possibly be. I discovered that the inconsistency was that the original data did not use the official table schema provided by TPH-C documentation. The old data had neglected to use primary and foreign keys during their trials.


A second set of challenges I encountered while benchmarking MonetDB. However, this was just an error on my part for not understand how MonetDB was structured. I had trouble at first creating the initial database because I had not realized there was no overlying administrative structure protecting the database on creation. With this new understanding of MonetDB’s administrative privileges, I was able to sail right through the MonetDB benchmarks. 

Conclusively, this project has allowed me to work with databases and engines that I would not have worked with otherwise. It has given me insight to perform critical thinking and problem solving regarding databases as well. Another big take-away I received is the comfortability of navigating without a graphical user interface. I originally did have my doubts about being thrown into a command line based operating system with no prior experience with terminal, but I quickly picked up on the syntax, commands, and became comfortable within the first week. Something else I took away from this project was definitely time management. If you put in more work at the beginning and keep ahead of your projects goals and due dates then you will have room for error and life as it happens.
