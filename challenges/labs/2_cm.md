#List all repo files
```
ls /etc/yum.repos.d/
CentOS-Base.repo       CentOS-Media.repo      mysql-community.repo
CentOS-Debuginfo.repo  CentOS-Vault.repo
CentOS-fasttrack.repo  cloudera-manager.repo
```

#SCM_prepare_database.sh

```
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql -h node00  --scm-host node01 scm scm password

```

```
JAVA_HOME=/usr/lib/jvm/jre-openjdk
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/lib/jvm/jre-openjdk/bin/java -cp /usr/share/java/mysql-connectorcloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properti
log4j:ERROR Could not find value for key log4j.appender.A
log4j:ERROR Could not instantiate appender named "A".
[2016-12-08 20:27:54,767] INFO     0[main] - com.cloudera.enterprise.dbutil.DbComase.
All done, your SCM database is configured correctly!
```
