# 查看rgw相关信息
radosgw-admin realm list # 查看rgw的realm<br>
{<br>
    "default_info": "3239ba52-ee88-4e69-acae-930d09da5cdd",<br>
    "realms": [<br>
        "test_ftimage_realm"<br>
    ]<br>
}<br>

radosgw-admin zonegroup list # 查看rgw的zonegroup<br>
{<br>
    "default_info": "63f03ee2-9785-4631-9908-23205b17e0c5",<br>
    "zonegroups": [<br>
        "test_ftimage_zg",<br>
        "default"<br>
    ]<br>
}<br>
radosgw-admin zone list # 查看rgw的zone<br>
{<br>
    "default_info": "67069c4a-335d-4fb2-9464-17b56f53b5c6",<br>
    "zones": [<br>
        "test_ftimage_zone",<br>
        "default"<br>
    ]<br>
}<br>


radosgw-admin realm create --rgw-realm=test_xxx_realm --default<br>
radosgw-admin zonegroup create --rgw-zonegroup=test_xxx_zg --master --default<br>
radosgw-admin zone create --rgw-zonegroup=test_xxx_zg --rgw-zone=test_xxx_zone --master --default<br>

ceph orch apply rgw test-xxx --realm=test_xxx_realm --zone=test_xxx_zone --placement="2 ceph-01 ceph-02"<br>


ceph orch ls<br>
ceph orch rm rgw.test-xxx<br>
