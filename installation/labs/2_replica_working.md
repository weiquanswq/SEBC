#MYSQL Installation & Replication Setup
## Steps
### 1 Install mysql-server on both server and replica node
### 2 modify ```/etc/my.cnf``` file

Append 2 lines in ```/etc/my.cnf``` file <b>--  master node</b>
```
[mysqld]
log-bin=mysql-bin
server-id=1
```
Append 1 line in ```/etc/my.cnf``` file <b>--  replica node</b>
```
[mysqld]
server-id=2
```

### 3 Restart ```mysqld``` service

###4 set up password protection on both server and replica node
use ``` /usr/bin/mysql_secure_installation```

 i)  Set password protection for the server
 
 ii) Revoke permissions for anonymous users
 
 iii)Permit remote privileged login
 
 iV) Remove test databases
 
 v)  Refresh privileges in memory
 
 vi) Refreshes the ```mysqld``` service
 
###5 Grant Replication Priviledges (Master Node)

```GRANT REPLICATION SLAVE ON *.* TO 'repl'@'ClouderaSEDC-Node01' IDENTIFIED BY 'password'```
```SET GLOBAL binlog_format = 'ROW';```
```FLUSH TABLES WITH READ LOCK;```
 
 Start second terminal session, check the maaster status;
 ```SHOW MASTER STATUS;```
 Take note of the filename and byte offset 
 ```+------------------+----------+--------------+------------------+-------------------+
| File             | Position | Binlog_Do_DB | Binlog_Ignore_DB | Executed_Gtid_Set |
+------------------+----------+--------------+------------------+-------------------+
| mysql-bin.000002 |      552 |              |                  |                   |
+------------------+----------+--------------+------------------+-------------------+
1 row in set (0.00 sec)
```

logout of the second terminal
 

 
 in the first terminal run ```UNLOCK TABLES;```. <b>TAKE NOTE!</b> (failure to do so, will cause deadlock)

###6 Configure replica node
```CHANGE MASTER TO MASTER_HOST='ClouderaSEDC-Node00', MASTER_USER='repl', MASTER_PASSWORD='password', MASTER_LOG_FILE='mysql-bin.000002', MASTER_LOG_POS=552;```

```START SLAVE;```

```show slave status \G```

Results:
```
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event			<--- should see this
                  Master_Host: ClouderaSEDC-Node00
                  Master_User: repl
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql-bin.000002
          Read_Master_Log_Pos: 552
               Relay_Log_File: mysqld-relay-bin.000002
                Relay_Log_Pos: 283
        Relay_Master_Log_File: mysql-bin.000002
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
          ...
          ...
```
