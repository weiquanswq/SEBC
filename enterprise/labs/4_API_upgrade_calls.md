#Upgrade Cloudera Manager
##Pre-Upgrade/ Backup for sql
```
sudo mkdir sql.bak
sudo cd sql.bak

mysqldump -u root -p cmserver > cmserver.sql
mysqldump -u root -p amon > amon.sql
mysqldump -u root -p rman > rman.sql
mysqldump -u root -p metastore > metastore.sql
mysqldump -u root -p hue > hue.sql
mysqldump -u root -p oozie > oozie.sql
```

##Modify ```/etc/my.cnf```
Include :
```
[mysqld]
max_connections = 100
```
Restart mysql
```service mysqld restart ```

##Stop Cloudera Server / agent services
```
sudo service cloudera-scm-server stop
sudo service cloudera-scm-agent stop
```
## disabled outdated cloudera-manager.repo
Include 
```
enabled=0
```

##Create new cloudera-manager.repo
```
vi /etc/yum.repos.d/cloudera-manager-latest.repo
```
Include :
```
[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RHEL or CentOS 6 x86_64
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/5/
gpgkey = https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1
```
By default, it is enabled

##Clean package and upgrade
```
sudo yum clean all
sudo yum upgrade -y cloudera-manager-server
``` 
```cloudera-manager-daemons cloudera-manager-agent``` will also be upgraded as they are dependencies of ```cloudera-manager-server```

##Start Cloudera Server service
```
sudo service cloudera-scm-server start
```

<b>upon logging in, it will have a wizard to guide through the upgrade</b>



#API Commands
##Report the latest available version of the API
```
curl -u weiquanswq:cloudera "http://node00:7180/api/version"
```
Result:
```
v14
```

##Report the CM version
```
curl -u weiquanswq:cloudera "http://node00:7180/api/v14/cm/version"
```
Result:
```
{
  "version" : "5.9.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20161006-1801",
  "gitHash" : "898a5e032c080e18833dfc58180761f6ef2ea351",
  "snapshot" : false
}
```

##List all CM users
```
curl -u weiquanswq:cloudera "http://node00:7180/api/v14/users"
```

Result:
```
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "weiquanswq",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```

##Report the database server in use by CM
```
curl -u weiquanswq:cloudera "http://node00:7180/api/v14/cm/scmDbInfo"
```

Result:
```
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```

