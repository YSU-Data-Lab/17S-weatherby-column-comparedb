**February Preface**

Became ill with a nasty sinus infection for the first portion of February. I don't remember the entirity of my progress from January 30, 2017 to February 20, 2017. I estimate that being ill has set me back aproximately two weeks worth. I will be working on this project a lot more than originally allotted to makeup for that lost time; I am highly optimistic that I can accomplish these tasks by the original deadline of March 7, 2017.

**February 20th, 2017** 

Picking up where I left off: Attempt to solve an issue where I cannot log into any other database except Aikin's original one. His is located within the monetdbfarm under the tpch database. Creating a new database under the same farm yields invalid credential exceptions. Attempted to create a new farm, named weatherbyfarm, and added a database called tpch. Any attempt to log into that database is met with the same results. I believe the user just needs to be granted permissions for the newly created database, but am unsure because I've never actually admined anything like this.

**Week, February 19th, 2017**

Completed benchmark testing on MonetDB. Took a bit of reading to diagnose my problems importing the tables and the data. MonetDB wants the exact file path to import data from .tbl files. It will not accept '~/file/path.tbl' Another thing is MonetDB takes in integer values slightly differently, not allowing me to specify a legth on them. Each time I tried it would spit back that it wasn't expecting me to do that. So I had to alter the MonetDB script a bit to make it work with the software. Otherwise, all went swimmingly after I remedied my log in issue.

**Feburary 23rd, 2017**

**Benchmark on MonetDB complete for 1 Gigabyte of data**
