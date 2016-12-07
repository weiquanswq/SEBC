

```
{
  "timestamp" : "2016-12-07T04:17:30.672Z",
  "clusters" : [ {
    "name" : "Weiquanswq - Dino",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "660602880"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "660602880"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2548196966"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "428"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ClouderaSEDC-Node00"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-38431885aca4fe628e0d549b8c228e45",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "d2ce9b6f-3c1e-431f-85a3-4f9409daf52a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "evp6zuzo9us1wc6mu1svk0idh"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b5jvptgjtsdmim147k8aksbgn"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "660602880"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d2vpteofnrbeub5e93nulyark"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-d051d4bd9a87e2be0b28613c406e11e6",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "a9c7fb4c-d1ad-4aec-938a-3dd1537455f3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7vyyoaj7mlmhmeb9ldk46nok5"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-fd16511392d6be15c37c02b864fa3b0c",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "7a9a2b85-07dc-43c9-b41c-a2da0519e3a3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "vezmukij993ni7diut3wqwgi"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ClouderaSEDC-Node00"
        }, {
          "name" : "database_password",
          "value" : "password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-fd16511392d6be15c37c02b864fa3b0c"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e7jx688iabrciionkdtkjj6ye"
          }, {
            "name" : "secret_key",
            "value" : "RymXjsHPsejSEZHwex7LTt93WHaZMJ"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ClouderaSEDC-Node00"
          }, {
            "name" : "oozie_database_password",
            "value" : "password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "660602880"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9kho6g8n7bbzj7q7vzeo7z11n"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "660602880"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/mnt/resource/yarn/nm,/var/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/mnt/resource/yarn/container-logs,/var/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1024"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "660602880"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4483"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "true"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "Ci5Sui8HIdgV3ZESzZWOiPHSdS4Vw5"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "f3cq121ew348lul9mwser6q9e"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-5f590fc0ca62090fd772a5f554b4060d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "41e6490d-87e6-48a7-98b8-d23c20fc0d9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eu89w1h004ncxv2jxfgalekyq"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-d051d4bd9a87e2be0b28613c406e11e6",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "a9c7fb4c-d1ad-4aec-938a-3dd1537455f3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "blfw36jpaznokq1sf0zueoaan"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-fd16511392d6be15c37c02b864fa3b0c",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "7a9a2b85-07dc-43c9-b41c-a2da0519e3a3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2ttgr5ivllqwz02o0xy4lc0tm"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "60"
          }, {
            "name" : "role_jceks_password",
            "value" : "9qx0yrg9to2awv5iyrgoalbvn"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "660602880"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/mnt/resource/dfs/dn,/var/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3104312115"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/var/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/mnt/resource/dfs/nn,/var/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "2305818624"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/mnt/resource/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "2305818624"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "QUPhl5Oi6WkeCrkum5iYEFTRVJ56tA"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "fqn4NONNHSrYJx3woWoQK7Tjujr7oi"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "XpyBHUZGrSpept4Z671CODhNk6OP7b"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-5f590fc0ca62090fd772a5f554b4060d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "41e6490d-87e6-48a7-98b8-d23c20fc0d9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bnf3q2sry1cknwbde7hb4me44"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-d051d4bd9a87e2be0b28613c406e11e6",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "a9c7fb4c-d1ad-4aec-938a-3dd1537455f3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ewjvx3qwd0zcdyb6jlb17b6ex"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-fd16511392d6be15c37c02b864fa3b0c",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "7a9a2b85-07dc-43c9-b41c-a2da0519e3a3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "epgyvktdnsx71xnp4zoeefv0v"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-d051d4bd9a87e2be0b28613c406e11e6",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "a9c7fb4c-d1ad-4aec-938a-3dd1537455f3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ei7ri4geov0njtpo72vqd7e2p"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-fd16511392d6be15c37c02b864fa3b0c",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "7a9a2b85-07dc-43c9-b41c-a2da0519e3a3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "zs7m11blsou3hgsa2a1j9xtn"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-411aa3e7b6ad03d36c09be1cd0be1a7e",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4l760g80fzr94y5ns9uz1h3qk"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-d051d4bd9a87e2be0b28613c406e11e6",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "a9c7fb4c-d1ad-4aec-938a-3dd1537455f3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1iqnodgntro7oj5d2058ve020"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-fd16511392d6be15c37c02b864fa3b0c",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "7a9a2b85-07dc-43c9-b41c-a2da0519e3a3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3x06v396gr4id8fgwyh9rql9"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-d051d4bd9a87e2be0b28613c406e11e6",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "a9c7fb4c-d1ad-4aec-938a-3dd1537455f3"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "69"
          }, {
            "name" : "role_jceks_password",
            "value" : "9tjatboqs6918rr6mamgqw0lr"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-fd16511392d6be15c37c02b864fa3b0c",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "7a9a2b85-07dc-43c9-b41c-a2da0519e3a3"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "62"
          }, {
            "name" : "role_jceks_password",
            "value" : "15awp7k3k2hgl32v6ja5h4dsi"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea",
    "ipAddress" : "172.16.7.4",
    "hostname" : "ClouderaSEDC-Node00",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "7a9a2b85-07dc-43c9-b41c-a2da0519e3a3",
    "ipAddress" : "172.16.7.5",
    "hostname" : "ClouderaSEDC-Node01",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "a9c7fb4c-d1ad-4aec-938a-3dd1537455f3",
    "ipAddress" : "172.16.7.6",
    "hostname" : "ClouderaSEDC-Node02",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "41e6490d-87e6-48a7-98b8-d23c20fc0d9a",
    "ipAddress" : "172.16.7.8",
    "hostname" : "ClouderaSEDC-Node03",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "d2ce9b6f-3c1e-431f-85a3-4f9409daf52a",
    "ipAddress" : "172.16.7.9",
    "hostname" : "ClouderaSEDC-Node04",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-411aa3e7b6ad03d36c09be1cd0be1a7e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "8e0472a3f9ca88e0db25be048b70d199eb22622fc827708abc17cc27490742cc",
    "pwSalt" : -7693568589716961793,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-411aa3e7b6ad03d36c09be1cd0be1a7e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "04612e2fe1527c185eadf7fd23863d5c2cff429628e0fd1ded759deafda8b0eb",
    "pwSalt" : 8190923151978451131,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-411aa3e7b6ad03d36c09be1cd0be1a7e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "921f5ee38493eada6cd8141ffeec0e9191673cbea0ad74b76a8f0728d4f838d7",
    "pwSalt" : 2969374645668047013,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-411aa3e7b6ad03d36c09be1cd0be1a7e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c34a03f0a3262cb9a32722605d765903e78ea5ee8c340c4a4fcdb65ddf451c57",
    "pwSalt" : -3371335457346273907,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "b9832b515911b2d30d7ac817363f9632c528095eb2f6f0ea0848f4b1255ba6b6",
    "pwSalt" : 5110208920984232162,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "85ce49f1839bc4700dff304d6ab393b81fc1d74d334e326e6735e362b103f8a8",
    "pwSalt" : 5022266213222175179,
    "pwLogin" : true
  }, {
    "name" : "weiquanswq",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "7512b79ff7c08e5ebf84e103c6b63614fc12caef8fb61a96e1938987ed76ae03",
    "pwSalt" : 3557467988335006977,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20160916-1426",
    "gitHash" : "d23c620f3a3bbd85d8511d6ebba49beaaab14b75",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "660602880"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "660602880"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "858783744"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ClouderaSEDC-Node00"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "660602880"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "660602880"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "858783744"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-411aa3e7b6ad03d36c09be1cd0be1a7e",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "812hom2pgwb9auv3ejlnujffh"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-411aa3e7b6ad03d36c09be1cd0be1a7e",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "b2cwttt4s170myb63x7tgo597"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-411aa3e7b6ad03d36c09be1cd0be1a7e",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4kvx5tvj4dvt6xdu5i38j45qu"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-411aa3e7b6ad03d36c09be1cd0be1a7e",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "84vvb1si8zer1t6y6few1tfwz"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-411aa3e7b6ad03d36c09be1cd0be1a7e",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "4bd01f18-5746-4469-9bf2-2fcf3538e8ea"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "53i8g96t8jlxafbgcoy2ybidj"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 20:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "NOT_ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/,http://archive.cloudera.com/cdh5/parcels/5.8.2/,http://172.16.7.4/parcels/"
    } ]
  }
}
```
