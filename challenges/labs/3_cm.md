#hdfs user list

```
[hduser@cdhsebcn01 ~]$ a hadoop fs -ls /user
Found 6 items
drwxrwxrwx   - mapred  hadoop           0 2016-12-08 21:00 /user/history
drwxrwxr-t   - hive    hive             0 2016-12-08 21:01 /user/hive
drwxrwxr-x   - hue     hue              0 2016-12-08 21:01 /user/hue
drwxrwxr-x   - oozie   oozie            0 2016-12-08 21:02 /user/oozie
drwxr-xr-x   - orchard orchard          0 2016-12-08 21:12 /user/orchard
drwxr-xr-x   - raffles raffles          0 2016-12-08 21:12 /user/raffles
```


#List all hosts - through API

```
 curl -u weiquanswq:cloudera "http://node01:7180/api/v14/hosts"
```

```
{
  "items" : [ {
    "hostId" : "af0fe28c-bdf3-4920-85b3-2d677b4233ec",
    "ipAddress" : "172.16.7.14",
    "hostname" : "cdhsebcn00",
    "rackId" : "/default",
    "hostUrl" : "http://cdhsebcn01:7180/cmf/hostRedirect/af0fe28c-bdf3-4920-85b3-2d677b4233ec",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14734823424
  }, {
    "hostId" : "4befe143-40f7-4885-8ac2-a364bdc15fa9",
    "ipAddress" : "172.16.7.15",
    "hostname" : "cdhsebcn01",
    "rackId" : "/default",
    "hostUrl" : "http://cdhsebcn01:7180/cmf/hostRedirect/4befe143-40f7-4885-8ac2-a364bdc15fa9",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14734823424
  }, {
    "hostId" : "73cf17cd-af30-49e2-8e29-68ca2d64978b",
    "ipAddress" : "172.16.7.16",
    "hostname" : "cdhsebcn02",
    "rackId" : "/default",
    "hostUrl" : "http://cdhsebcn01:7180/cmf/hostRedirect/73cf17cd-af30-49e2-8e29-68ca2d64978b",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14734823424
  }, {
    "hostId" : "9f473a4c-e59c-4552-bb0b-390475b7a7dd",
    "ipAddress" : "172.16.7.17",
    "hostname" : "cdhsebcn03",
    "rackId" : "/default",
    "hostUrl" : "http://cdhsebcn01:7180/cmf/hostRedirect/9f473a4c-e59c-4552-bb0b-390475b7a7dd",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14734823424
  }, {
    "hostId" : "690ec1e7-497a-4c14-bfb7-1d54deeb1d32",
    "ipAddress" : "172.16.7.18",
    "hostname" : "cdhsebcn04",
    "rackId" : "/default",
    "hostUrl" : "http://cdhsebcn01:7180/cmf/hostRedirect/690ec1e7-497a-4c14-bfb7-1d54deeb1d32",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14734823424
  } ]
}
```
