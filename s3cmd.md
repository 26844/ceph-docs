### s3cmd命令
#### 在centos7 安装 
pip install s3cmd
#### 在ubuntu22.04 安装
apt install s3cmd

#### s3cmd 配置
s3cmd --configure

New settings:
  Access Key: xxxx
  Secret Key: yyyy
  Default Region: zzzz
  S3 Endpoint: 114.55.65.30:80
  DNS-style bucket+hostname:port template for accessing a bucket: %(bucket)s.s3.amazonaws.com
  Encryption password: 
  Path to GPG program: /usr/bin/gpg
  Use HTTPS protocol: False
  HTTP Proxy server name: 
  HTTP Proxy server port: 0

Test access with supplied credentials? [Y/n] Y
Please wait, attempting to list all buckets...
Success. Your access key and secret key worked fine :-)

Now verifying that encryption works...
Not configured. Never mind.

Save settings? [y/N] Y
Configuration saved to '/root/.s3cfg'

其中  Default Region: zzzz 的值，使用radosgw-admin zonegroup list命令查看

#### 列出所有buckets
s3cmd ls
2024-08-27 03:19  s3://new-bucket-test
