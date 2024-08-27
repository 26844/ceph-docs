## ceph用户
### 创建用户
radosgw-admin user create --uid=xxxapi --display-name="xxx s3 api" --email=test@xx.com


### 查看某用户信息
radosgw-admin user info --uid=xxx

### 查看某用户用量统计
radosgw-admin user stats --uid=xxx
