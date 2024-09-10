#### RGW - Ceph 对象网关

##### 创建自定义realm
###### radosgw-admin realm create --rgw-realm=test_xxx_realm --default<br>
##### 创建自定义zonegroup
###### radosgw-admin zonegroup create --rgw-zonegroup=test_xxx_zg --master --default<br>
##### 创建自定义zone
###### radosgw-admin zone create --rgw-zonegroup=test_xxx_zg --rgw-zone=test_xxx_zone --master --default<br>
##### 命令行中使用 ceph orch 命令部署自定义 Ceph 对象网关，创建成功后会在ceph-01和ceph-02主机上启动80端口，即endpoint地址：ceph-01ip:80，ceph-02ip:80
###### ceph orch apply rgw test-xxx --realm=test_xxx_realm --zone=test_xxx_zone --placement="2 ceph-01 ceph-02"<br>

##### 查看各节点 rgw 是否启动
###### ceph orch ps --daemon-type rgw

##### 列出rgw的realm<br>
###### radosgw-admin realm list<br>
{<br>
    "default_info": "3239ba52-ee88-4e69-acae-930d09da5cdd",<br>
    "realms": [<br>
        "test_xxx_realm"<br>
    ]<br>
}<br>

##### 列出rgw的zonegroup<br>
###### radosgw-admin zonegroup list<br> 
{<br>
    "default_info": "63f03ee2-9785-4631-9908-23205b17e0c5",<br>
    "zonegroups": [<br>
        "test_xxx_zg",<br>
        "default"<br>
    ]<br>
}<br>

##### 列出rgw的zone<br>
####### radosgw-admin zone list<br> 
{<br>
    "default_info": "67069c4a-335d-4fb2-9464-17b56f53b5c6",<br>
    "zones": [<br>
        "test_xxx_zone",<br>
        "default"<br>
    ]<br>
}<br>

##### 删除 Ceph 对象网关
###### ceph orch rm rgw.test-xxx<br>

##### 创建用户，会生成ak\sk
###### radosgw-admin user create --uid=xxxapi --display-name="xxx s3 api" --email=test@xx.com


##### 查看某用户信息,包含ak\sk信息
###### radosgw-admin user info --uid=xxx

##### 查看某用户用量统计
###### radosgw-admin user stats --uid=xxx

##### 列出桶名
###### radosgw-admin bucket list

