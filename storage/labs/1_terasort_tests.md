#Test HDFS Performance

## Create end user Lnux account 
```
sudo useradd weiquanswq
sudo passwd weiquanswq
```
## Create home HDFS directory 
Creating home directory as ```hdfs``` user and which change the ownership to ```weiquanswq``` user
```
sudo -u hdfs hadoop fs -mkdir /user/weiquanswq
sudo -u hdfs hadoop fs -chown weiquanswq:weiquanswq /user/weiquanswq 
```

##Create a 10 GB file using ```teragen```
 - Set the number of mappers to four
 - Limit the block size to 32 MB
 
The number of splits is depends on the number of mapper. In this case, it will contributes to 4 parts.
 ```
 time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -D dfs.blocksize=32m 100000000 /user/weiquanswq/teragen-10GB 
 ```
 
 Results: 
 ```
 
6/12/06 00:43:33 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=494408
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=531697
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=531697
                Total vcore-seconds taken by all map tasks=531697
                Total megabyte-seconds taken by all map tasks=544457728
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1008
                CPU time spent (ms)=131300
                Physical memory (bytes) snapshot=683937792
                Virtual memory (bytes) snapshot=6252625920
                Total committed heap usage (bytes)=828899328
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000
```

Time : 
```
real    2m26.362s
user    0m4.671s
sys     0m0.273s
```
Files : 
```
hadoop fs -ls ./teragen-10GB
Found 5 items
-rw-r--r--   3 weiquanswq weiquanswq          0 2016-12-06 00:43 teragen-10GB/_SUCCESS
-rw-r--r--   3 weiquanswq weiquanswq 2500000000 2016-12-06 00:43 teragen-10GB/part-m-00000
-rw-r--r--   3 weiquanswq weiquanswq 2500000000 2016-12-06 00:43 teragen-10GB/part-m-00001
-rw-r--r--   3 weiquanswq weiquanswq 2500000000 2016-12-06 00:43 teragen-10GB/part-m-00002
-rw-r--r--   3 weiquanswq weiquanswq 2500000000 2016-12-06 00:43 teragen-10GB/part-m-00003
```

## Run the ```terasort``` command on the file generated
Reading data from ```  /user/weiquanswq/teragen-10GB``` and output results at ```/user/weiquanswq/terasort-10GB``` 
In this command, it will utilise both Map and Reduce.
```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/weiquanswq/teragen-10GB /user/weiquanswq/terasort-10GB
```

Result :
```

16/12/06 00:53:59 INFO mapreduce.Job: Job job_1480996981249_0007 completed successfully
16/12/06 00:53:59 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=4483389024
                FILE: Number of bytes written=8896833856
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10000037800
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=918
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=300
                Launched reduce tasks=6
                Data-local map tasks=300
                Total time spent by all maps in occupied slots (ms)=1426355
                Total time spent by all reduces in occupied slots (ms)=678583
                Total time spent by all map tasks (ms)=1426355
                Total time spent by all reduce tasks (ms)=678583
                Total vcore-seconds taken by all map tasks=1426355
                Total vcore-seconds taken by all reduce tasks=678583
                Total megabyte-seconds taken by all map tasks=1460587520
                Total megabyte-seconds taken by all reduce tasks=694868992
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Map output bytes=10200000000
                Map output materialized bytes=4375170195
                Input split bytes=37800
                Combine input records=0
                Combine output records=0
                Reduce input groups=100000000
                Reduce shuffle bytes=4375170195
                Reduce input records=100000000
                Reduce output records=100000000
                Spilled Records=200000000
                Shuffled Maps =1800
                Failed Shuffles=0
                Merged Map outputs=1800
                GC time elapsed (ms)=21063
                CPU time spent (ms)=981070
                Physical memory (bytes) snapshot=148992880640
                Virtual memory (bytes) snapshot=480157626368
                Total committed heap usage (bytes)=168598962176
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10000000000
        File Output Format Counters
                Bytes Written=10000000000
16/12/06 00:53:59 INFO terasort.TeraSort: done

```

Time : 
```
real    6m15.192s
user    0m7.509s
sys     0m0.339s
```

Files :
```
hadoop fs -ls ./terasort-10GB
Found 8 items
-rw-r--r--   1 weiquanswq weiquanswq          0 2016-12-06 00:53 terasort-10GB/_SUCCESS
-rw-r--r--  10 weiquanswq weiquanswq         55 2016-12-06 00:47 terasort-10GB/_partition.lst
-rw-r--r--   1 weiquanswq weiquanswq 1657210500 2016-12-06 00:53 terasort-10GB/part-r-00000
-rw-r--r--   1 weiquanswq weiquanswq 1669051200 2016-12-06 00:53 terasort-10GB/part-r-00001
-rw-r--r--   1 weiquanswq weiquanswq 1654375500 2016-12-06 00:53 terasort-10GB/part-r-00002
-rw-r--r--   1 weiquanswq weiquanswq 1668843100 2016-12-06 00:53 terasort-10GB/part-r-00003
-rw-r--r--   1 weiquanswq weiquanswq 1681409800 2016-12-06 00:53 terasort-10GB/part-r-00004
-rw-r--r--   1 weiquanswq weiquanswq 1669109900 2016-12-06 00:53 terasort-10GB/part-r-00005
```
