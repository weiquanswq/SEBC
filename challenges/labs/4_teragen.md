#Teragen command
```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 -D dfs.blocksize=64m 51200000 /user/raffles/tgen512m
```

results:
```

time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop                                                                                       -0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 dfs.blocksize=64                                                                                       m 51200000 /user/raffles/tgen512m^C
[raffles@cdhsebcn00 hduser]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop                                                                                       -0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=8 -D dfs.blocksize                                                                                       =64m 51200000 /user/raffles/tgen512m
16/12/08 21:35:05 INFO client.RMProxy: Connecting to ResourceManager at cdhsebcn0                                                                                       0/172.16.7.14:8032
16/12/08 21:35:05 INFO terasort.TeraSort: Generating 51200000 using 8
16/12/08 21:35:05 INFO mapreduce.JobSubmitter: number of splits:8
16/12/08 21:35:05 INFO Configuration.deprecation: mapred.map.tasks is deprecated.                                                                                        Instead, use mapreduce.job.maps
16/12/08 21:35:05 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_148                                                                                       1252433140_0001
16/12/08 21:35:06 INFO impl.YarnClientImpl: Submitted application application_148                                                                                       1252433140_0001
16/12/08 21:35:06 INFO mapreduce.Job: The url to track the job: http://cdhsebcn00                                                                                       :8088/proxy/application_1481252433140_0001/
16/12/08 21:35:06 INFO mapreduce.Job: Running job: job_1481252433140_0001
16/12/08 21:35:12 INFO mapreduce.Job: Job job_1481252433140_0001 running in uber                                                                                        mode : false
16/12/08 21:35:12 INFO mapreduce.Job:  map 0% reduce 0%
16/12/08 21:35:24 INFO mapreduce.Job:  map 16% reduce 0%
16/12/08 21:35:32 INFO mapreduce.Job:  map 36% reduce 0%
16/12/08 21:35:35 INFO mapreduce.Job:  map 50% reduce 0%
16/12/08 21:35:38 INFO mapreduce.Job:  map 54% reduce 0%
16/12/08 21:35:39 INFO mapreduce.Job:  map 56% reduce 0%
16/12/08 21:35:41 INFO mapreduce.Job:  map 65% reduce 0%
16/12/08 21:35:44 INFO mapreduce.Job:  map 73% reduce 0%
16/12/08 21:35:46 INFO mapreduce.Job:  map 75% reduce 0%
16/12/08 21:35:51 INFO mapreduce.Job:  map 83% reduce 0%
16/12/08 21:35:53 INFO mapreduce.Job:  map 91% reduce 0%
16/12/08 21:35:54 INFO mapreduce.Job:  map 95% reduce 0%
16/12/08 21:35:56 INFO mapreduce.Job:  map 96% reduce 0%
16/12/08 21:36:00 INFO mapreduce.Job:  map 97% reduce 0%
16/12/08 21:36:02 INFO mapreduce.Job:  map 100% reduce 0%
16/12/08 21:36:04 INFO mapreduce.Job: Job job_1481252433140_0001 completed successfully
16/12/08 21:36:05 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=978683
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=682
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=32
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=8
                Other local map tasks=8
                Total time spent by all maps in occupied slots (ms)=203784
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=203784
                Total vcore-seconds taken by all map tasks=203784
                Total megabyte-seconds taken by all map tasks=208674816
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Input split bytes=682
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1155
                CPU time spent (ms)=84740
                Physical memory (bytes) snapshot=2819776512
                Virtual memory (bytes) snapshot=12498042880
                Total committed heap usage (bytes)=2969042944
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=109963291816450258
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=5120000000

```

#time
```
real    1m1.976s
user    0m4.466s
sys     0m0.223s

```

#file Output
command
```
hadoop fs -ls /user/raffles/tgen512m
```

Result:
```
[raffles@cdhsebcn00 hduser]$ hadoop fs -ls /user/raffles/tgen512m
Found 9 items
-rw-r--r--   3 raffles raffles          0 2016-12-08 21:36 /user/raffles/tgen512m/_SUCCESS
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:35 /user/raffles/tgen512m/part-m-00000
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:35 /user/raffles/tgen512m/part-m-00001
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:35 /user/raffles/tgen512m/part-m-00002
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:35 /user/raffles/tgen512m/part-m-00003
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:35 /user/raffles/tgen512m/part-m-00004
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:35 /user/raffles/tgen512m/part-m-00005
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:35 /user/raffles/tgen512m/part-m-00006
-rw-r--r--   3 raffles raffles  640000000 2016-12-08 21:36 /user/raffles/tgen512m/part-m-00007
```


#FSCK check
```
[raffles@cdhsebcn00 hduser]$ hadoop fsck /user/raffles/tgen512m
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://cdhsebcn00:50070
FSCK started by raffles (auth:SIMPLE) from /172.16.7.14 for path /user/raffles/tgen512m at Thu Dec 08 21:40:51 CST 2016
.........Status: HEALTHY
 Total size:    5120000000 B
 Total dirs:    1
 Total files:   9
 Total symlinks:                0
 Total blocks (validated):      80 (avg. block size 64000000 B)
 Minimally replicated blocks:   80 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Thu Dec 08 21:40:51 CST 2016 in 5 milliseconds


The filesystem under path '/user/raffles/tgen512m' is HEALTHY

```


