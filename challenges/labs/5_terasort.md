#Terasort
```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/raffles/tgen512m /user/raffles/tsort512m
```
```

[raffles@cdhsebcn00 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20                                                                                       -mapreduce/hadoop-examples.jar terasort /user/raffles/tgen512m /user/raffles/tsor                                                                                       t512m
16/12/08 21:59:06 INFO terasort.TeraSort: starting
16/12/08 21:59:07 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION                                                                                       _TOKEN owner=raffles@DINO.SG, renewer=yarn, realUser=, issueDate=1481255947473, m                                                                                       axDate=1481860747473, sequenceNumber=1, masterKeyId=2 on 172.16.7.14:8020
16/12/08 21:59:07 INFO security.TokenCache: Got dt for hdfs://cdhsebcn00:8020; Ki                                                                                       nd: HDFS_DELEGATION_TOKEN, Service: 172.16.7.14:8020, Ident: (token for raffles:                                                                                        HDFS_DELEGATION_TOKEN owner=raffles@DINO.SG, renewer=yarn, realUser=, issueDate=1                                                                                       481255947473, maxDate=1481860747473, sequenceNumber=1, masterKeyId=2)
16/12/08 21:59:07 INFO input.FileInputFormat: Total input paths to process : 8
Spent 284ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 288ms
Sampling 10 splits of 80
Making 6 from 100000 sampled records
Computing parititions took 623ms
Spent 913ms computing partitions.
16/12/08 21:59:08 INFO client.RMProxy: Connecting to ResourceManager at cdhsebcn0                                                                                       0/172.16.7.14:8032
16/12/08 21:59:08 INFO mapreduce.JobSubmitter: number of splits:80
16/12/08 21:59:08 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_148                                                                                       1255820046_0001
16/12/08 21:59:08 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Servi                                                                                       ce: 172.16.7.14:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raff                                                                                       les@DINO.SG, renewer=yarn, realUser=, issueDate=1481255947473, maxDate=1481860747                                                                                       473, sequenceNumber=1, masterKeyId=2)
16/12/08 21:59:09 INFO impl.YarnClientImpl: Submitted application application_148                                                                                       1255820046_0001
16/12/08 21:59:09 INFO mapreduce.Job: The url to track the job: http://cdhsebcn00                                                                                       :8088/proxy/application_1481255820046_0001/
16/12/08 21:59:09 INFO mapreduce.Job: Running job: job_1481255820046_0001
16/12/08 21:59:12 INFO mapreduce.Job: Job job_1481255820046_0001 running in uber mode : false
16/12/08 21:59:12 INFO mapreduce.Job:  map 0% reduce 0%
16/12/08 21:59:12 INFO mapreduce.Job: Job job_1481255820046_0001 failed with state FAILED due to: Application application_1481255820046_0001 failed 2 times due to AM Container for appattempt_1481255820046_0001_000002 exited with  exitCode: -1000
For more detailed output, check application tracking page:http://cdhsebcn00:8088/proxy/application_1481255820046_0001/Then, click on links to logs of each attempt.
Diagnostics: Application application_1481255820046_0001 initialization failed (exitCode=255) with output: main : command provided 0
main : run as user is raffles
main : requested yarn user is raffles
User raffles not found

Failing this attempt. Failing the application.
16/12/08 21:59:12 INFO mapreduce.Job: Counters: 0
16/12/08 21:59:12 INFO terasort.TeraSort: done

real    0m7.546s
user    0m5.544s
sys     0m0.239s

```
