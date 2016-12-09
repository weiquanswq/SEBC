
#Challenge Set up
Region : South East Asia

OS: Centos6.7

Vms: Azure DS3v3.  ( refer to ds3v2.png)


#volume space you have available on each node
```
df -kh
```
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda2        20G  2.1G   18G  11% /
tmpfs           6.9G     0  6.9G   0% /dev/shm
/dev/sda1       488M   93M  370M  21% /boot
/dev/sda3        29G  194M   28G   1% /var
/dev/sdb1        28G   44M   26G   1% /mnt/resource
```


```
sudo yum repolist enabled
```
```
Loaded plugins: fastestmirror, security
Loading mirror speeds from cached hostfile
repo id               repo name                                            stat
base                  CentOS-6 - Base                                      6,69
extras                CentOS-6 - Extras                                       6
openlogic             CentOS-6 - openlogic packages for x86_64                6
updates               CentOS-6 - Updates                                     68
repolist: 7,511
```

##password
```
/etc/passwd
```
```
raffles:x:2700:2700::/home/raffles:/bin/bash
orchard:x:2800:2800::/home/orchard:/bin/bash
```

##group
```
/etc/group
```
```
shops:x:2801:orchard
walks:x:2802:raffles
```
