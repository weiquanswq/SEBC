# Cloudera Manager repo file
```
sudo vi /etc/yum.repos.d/cloudera-manager.repo
```

```
[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RHEL or CentOS 6 x86_64
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/5/
gpgkey = https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1
```