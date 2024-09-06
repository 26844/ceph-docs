### s3cmd命令
#### 在centos7 安装 
##### pip install s3cmd
#### 在ubuntu22.04 安装
##### apt install s3cmd

#### s3cmd 配置
##### s3cmd --configure

New settings:<br>
  Access Key: xxxx<br>
  Secret Key: yyyy<br>
  Default Region: zzzz<br>
  S3 Endpoint: 114.55.65.30:80<br>
  DNS-style bucket+hostname:port template for accessing a bucket: %(bucket)s.s3.amazonaws.com<br>
  Encryption password: <br>
  Path to GPG program: /usr/bin/gpg<br>
  Use HTTPS protocol: False<br>
  HTTP Proxy server name: <br>
  HTTP Proxy server port: 0<br>

Test access with supplied credentials? [Y/n] Y<br>
Please wait, attempting to list all buckets...<br>
Success. Your access key and secret key worked fine :-)<br>

Now verifying that encryption works...<br>
Not configured. Never mind.<br>

Save settings? [y/N] Y<br>
Configuration saved to '/root/.s3cfg'<br>

其中  Default Region: zzzz 的值，使用radosgw-admin zonegroup list命令查看<br>

#### 列出所有buckets
##### s3cmd ls
2024-08-27 03:19  s3://new-bucket-test
