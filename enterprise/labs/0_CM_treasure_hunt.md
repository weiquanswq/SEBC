##What is ubertask optimization?
enables grouping several small tasks of a job on a single JVM

##Where in CM is the Kerberos Security Realm value displayed?
Cloudera Manager > Administration tab > Settings > 

##Which CDH service(s) host a property for enabling Kerberos authentication?
hive, zookeeper, hue, oozie,hdfs, yarn

##How do you upgrade the CM agents?
 use an upgrade wizard that is invoked when connect to the Admin Console or manually install the Cloudera Manager Agent packages

##Give the tsquery statement used to chart Hue's CPU utilization?
```select stats(cpu_user_rate, counter) + stats(cpu_system_rate, counter) where roleType=HUE_SERVER```
##Name all the roles that make up the Hive service
Gateway, Hive Metastore Server, HiveServer2
##What steps must be completed before integrating Cloudera Manager with Kerberos?
 1. Set a working KDC
 2. KDC allows renewable tickets
 3. Installed OpenLdap client libraries
 4. Created an account with premission to create other accounts in KDC
