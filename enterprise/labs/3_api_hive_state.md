#Control Hive Services through API Curl

<b>! Take Note</b>

The cluster name is <b>Case Sensitive</b> and  replace 'space' with ```%20````
eg. ```.../clusters/Weiquanswq%20-%20Dino/...```


##Start 
```
curl -X POST -u weiquanswq:cloudera 'http://node00:7180/api/v12/clusters/Weiquanswq%20-%20Dino/services/hive/commands/start'
```

Result :
```
  
{
  "id" : 459,
  "name" : "Start",
  "startTime" : "2016-12-07T04:32:42.801Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
```

##Stop 
```
curl -X POST -u weiquanswq:cloudera 'http://node00:7180/api/v12/clusters/Weiquanswq%20-%20Dino/services/hive/commands/stop'
```

Result :
```
{
  "id" : 456,
  "name" : "Stop",
  "startTime" : "2016-12-07T04:32:17.083Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
```


##Check Status 
```
curl -X GET -u weiquanswq:cloudera 'http://node00:7180/api/v12/clusters/Weiquanswq%20-%20Dino/services/hive'
```

Result :
```

{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ClouderaSEDC-Node00:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ClouderaSEDC-Node00:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"

```
