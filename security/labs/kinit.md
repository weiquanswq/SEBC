#Access fail

```
hadoop fs -ls /
```
Error :
```
...
...
ls: Failed on local exception: java.io.IOException: javax.security.sasl.SaslException: GSS initiate failed [Caused by GSSException: No valid credentials provided (Mechanism level: Failed to find any Kerberos tgt)]; Host Details : local host is: "clouderasedc-node00/172.16.7.4"; destination host is: "clouderasedc-node02":8020;
```


#kinit
Create access ticket
```
[weiquanswq@clouderasedc-node00 ~] kinit
Password for weiquanswq@EXAMPLE.COM:
```

#klist
```
[weiquanswq@clouderasedc-node00 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_501
Default principal: weiquanswq@EXAMPLE.COM

Valid starting     Expires            Service principal
12/08/16 00:45:59  12/09/16 00:45:59  krbtgt/EXAMPLE.COM@EXAMPLE.COM
        renew until 12/08/16 00:45:59
[weiquanswq@clouderasedc-node00 ~]$
```
