# Replicate to Another Cluster 

## Generating 500 MB files
```
hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen 5242880 /dino/terasort-inputrob
```
## Transferring to my partner, cxinyi.

<b>! TAKE NOTE</b>

For Azure, has to allow port for other access (Network Security Group)
Address has to be NameNode address.

```
hdfs hadoop distcp /dino/terasort-input hdfs://52.163.49.151/test
```

Results:
```
6/12/05 22:23:24 INFO mapreduce.Job: Counters: 33
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=379686
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=524289648
                HDFS: Number of bytes written=524288000
                HDFS: Number of read operations=57
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=13
        Job Counters
                Launched map tasks=3
                Other local map tasks=3
                Total time spent by all maps in occupied slots (ms)=15768
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=15768
                Total vcore-seconds taken by all map tasks=15768
                Total megabyte-seconds taken by all map tasks=16146432
        Map-Reduce Framework
                Map input records=4
                Map output records=0
                Input split bytes=342
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=118
                CPU time spent (ms)=7770
                Physical memory (bytes) snapshot=732205056
                Virtual memory (bytes) snapshot=4718686208
                Total committed heap usage (bytes)=1076363264
        File Input Format Counters
                Bytes Read=1306
        File Output Format Counters
                Bytes Written=0
        org.apache.hadoop.tools.mapred.CopyMapper$Counter
                BYTESCOPIED=524288000
                BYTESEXPECTED=524288000
                COPY=4
```

##Browse results

```
hadoop fsck /dino/terasort-input -files -blocks
```
```
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ClouderaSEDC-Node01:50070
FSCK started by hdfs (auth:SIMPLE) from /172.16.7.4 for path /dino/terasort-input at Mon Dec 05 23:13:20 CST 2016
/dino/terasort-input <dir>
/dino/terasort-input/_SUCCESS 0 bytes, 0 block(s):  OK

/dino/terasort-input/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-196030094-172.16.7.5-1480993726139:blk_1073742587_1763 len=134217728 Live_repl=3
1. BP-196030094-172.16.7.5-1480993726139:blk_1073742589_1765 len=127926272 Live_repl=3

/dino/terasort-input/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-196030094-172.16.7.5-1480993726139:blk_1073742588_1764 len=134217728 Live_repl=3
1. BP-196030094-172.16.7.5-1480993726139:blk_1073742590_1766 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Mon Dec 05 23:13:20 CST 2016 in 3 milliseconds


The filesystem under path '/dino/terasort-input' is HEALTHY

```
