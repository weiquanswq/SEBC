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
