## ceph用户
### 列出存储集群中的用户
ceph auth list

### 创建用户
radosgw-admin user create --uid=xxxapi --display-name="xxx s3 api" --email=test@xx.cn


### 查看某用户信息
radosgw-admin user info --uid=xxx
