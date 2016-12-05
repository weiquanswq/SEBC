
#1. Check vm.swappiness on all your nodes

```
sudo vi /etc/systctl.conf
```
Result
```
...
kernel.shmall = 4294967296
vm.swappiness=1
net.ipv4.tcp_timestamps=0
net.ipv4.tcp_sack=1
```

#2. Show the mount attributes of all volumes
``` sudo mount -l```

Result

```
/dev/sda2 on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw)
/dev/sda1 on /boot type ext4 (rw)
/dev/sda3 on /var type ext4 (rw)
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
/dev/sdb1 on /mnt/resource type ext4 (rw)
```
#3. Show the reserve space of any non-root, ext-based volumes
```
sudo tune2fs -m 0 /dev/sda2
```
```
sudo tune2fs -l /dev/sda2
tune2fs 1.41.12 (17-May-2010)
Filesystem volume name:   <none>
Last mounted on:          /
Filesystem UUID:          003914c2-ef4e-4f44-80c4-9d085be29a78
Filesystem magic number:  0xEF53
Filesystem revision #:    1 (dynamic)
Filesystem features:      has_journal ext_attr resize_inode dir_index filetype needs_recovery extent flex_bg sparse_super large_file huge_file uninit_bg dir_nlink extra_isize
Filesystem flags:         signed_directory_hash
Default mount options:    user_xattr acl
Filesystem state:         clean
Errors behavior:          Continue
Filesystem OS type:       Linux
Inode count:              1310720
Block count:              5242880
Reserved block count:     0
...
```
#4. Show that transparent hugepages is disabled
```
sudo vi /etc/rc.local
```
Append if neccessary
Result
```
touch /var/lock/subsys/local
for i in `ls /sys/block/sd*/queue/scheduler`
do
echo "noop" > $i
done
echo never > /sys/kernel/mm/redhat_transparent_hugepage/enabled
echo never > /sys/kernel/mm/redhat_transparent_hugepage/defrag
```

Add  ```transparent_hugepage=never``` at the end of kernel line in ```/boot/grub/grub.conf```

#5. Report the network interface attributes
off IPv6
```
sudo vi /etc/sysctl.conf
```
Include this parameters if missing:
```
net.ipv4.tcp_low_latency=1
net.ipv4.tcp_adv_win_scale=1
net.ipv6.conf.all.disable_ipv6=1
```
Check
```
sysctl -p
```
Alternate Check
```
sudo ifconfig

eth0      Link encap:Ethernet  HWaddr 00:0D:3A:A2:A9:31
          inet addr:172.16.7.4  Bcast:172.16.7.255  Mask:255.255.255.0
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:25714 errors:0 dropped:0 overruns:0 frame:0
          TX packets:29404 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:4985897 (4.7 MiB)  TX bytes:4585258 (4.3 MiB)

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:131 errors:0 dropped:0 overruns:0 frame:0
          TX packets:131 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:26532 (25.9 KiB)  TX bytes:26532 (25.9 KiB)
```

# 6. Show forward and reverse host lookups using ```getent``` and ```nslookup```

Required to install bind-utils
```
sudo yum install -y bind-utils
```
getent command
```getent hosts```
Results:
```
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
172.16.7.4      ClouderaSEDC-Node00 node00
172.16.7.5      ClouderaSEDC-Node01 node01
172.16.7.6      ClouderaSEDC-Node02 node02
172.16.7.8      ClouderaSEDC-Node03 node03
172.16.7.9      ClouderaSEDC-Node04 node04
```

# 7. Verify the ncsd service is running
Required to install 
```
sudo yum install nscd 
sudo service  nscd start
sudo chkconfig nscd on
```
Results

``` sudo service nscd status

nscd (pid 5846) is running...```

#8. Verify the ntpd service is running
Sychronise to server
```
sudo ntpdate -u 0.centos.pool.ntp.org
```
Result
```
ntpstat
synchronised to NTP server (128.199.123.83) at stratum 3
   time correct to within 8297 ms
   polling server every 64 s
```


# Others:
Disable SElinux
```
vi /etc/selinux/conf
```
Change ```SELINUX=enforcing``` to ``` SELINUX=disabled```
```
# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of these two values:
#     targeted - Targeted processes are protected,
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted
```
