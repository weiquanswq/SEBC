# Test HDFS Snapshots

## Create a ```precious``` directory in HDFS and put the a file in
```
sudo -u hdfs hadoop fs -mkdir /precious
sudo mv ~/SEBC-master.zip /var/lib/hadoop-hdfs
sudo -u hdfs -i 

hadoop fs -put SEBC-master.zip /precious
hadoop fs -touchz abc.txt /precious
```

##Enable snapshots 
Through Cloudera Manager 
HDFS > file browser > /precious > enable snapshot

<b>Created snapshots called ```sebc-hdfs-test``` and ```sebc-hdfs-test-123```</b>

##Delete directory ```/precious```
```
hadoop fs -rm -r /precious
```
Result :
```
rm: Failed to move to trash: hdfs://nameservice1/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
```

##Delete file ```/precious/abc.txt```
```
hadoop fs -rm /precious/abc.txt
```
Result :
```
16/12/06 01:30:28 INFO fs.TrashPolicyDefault: Moved: 'hdfs://nameservice1/precious/abc.txt' to trash at: hdfs://nameservice1/user/hdfs/.Trash/Current/precious/abc.txt1481009428683
```

## Restore file 
```
hadoop fs -cp /precious/.snapshot/sebc-hdfs-test-123/abc.txt /precious
```
Can be done through Cloudera Manager as well.
Cluster > HDFS > File Browser > select drop-down menu next to the full file path  > Restore Directory From Snapshot


