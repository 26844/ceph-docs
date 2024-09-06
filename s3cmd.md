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

##### /root/.s3cfg
[default]
access_key = xxxx
access_token =
add_encoding_exts =
add_headers =
bucket_location = zzzz
ca_certs_file =
cache_file =
check_ssl_certificate = False
check_ssl_hostname = False
cloudfront_host = cloudfront.amazonaws.com
connection_max_age = 5
connection_pooling = True
content_disposition =
content_type =
default_mime_type = binary/octet-stream
delay_updates = False
delete_after = False
delete_after_fetch = False
delete_removed = False
dry_run = False
enable_multipart = True
encrypt = False
expiry_date =
expiry_days =
expiry_prefix =
follow_symlinks = False
force = False
get_continue = False
gpg_command = /usr/bin/gpg
gpg_decrypt = %(gpg_command)s -d --verbose --no-use-agent --batch --yes --passphrase-fd %(passphrase_fd)s -o %(output_file)s %(input_file)s
gpg_encrypt = %(gpg_command)s -c --verbose --no-use-agent --batch --yes --passphrase-fd %(passphrase_fd)s -o %(output_file)s %(input_file)s
gpg_passphrase =
guess_mime_type = True
host_base = 114.55.65.30:80
#host_bucket = %(bucket)s.s3.amazonaws.com
host_bucket = ip/%(bucket)
human_readable_sizes = False
invalidate_default_index_on_cf = False
invalidate_default_index_root_on_cf = True
invalidate_on_cf = False
keep_dirs = False
kms_key =
limit = -1
limitrate = 0
list_allow_unordered = False
list_md5 = False
log_target_prefix =
long_listing = False
max_delete = -1
max_retries = 5
mime_type =
multipart_chunk_size_mb = 15
multipart_copy_chunk_size_mb = 1024
multipart_max_chunks = 10000
preserve_attrs = True
progress_meter = True
proxy_host =
proxy_port = 0
public_url_use_https = False
put_continue = False
recursive = False
recv_chunk = 65536
reduced_redundancy = False
requester_pays = False
restore_days = 1
restore_priority = Standard
secret_key = yyyy
send_chunk = 65536
server_side_encryption = False
signature_v2 = False
signurl_use_https = False
simpledb_host = sdb.amazonaws.com
skip_destination_validation = False
skip_existing = False
socket_timeout = 300
ssl_client_cert_file =
ssl_client_key_file =
stats = False
stop_on_error = False
storage_class =
throttle_max = 100
upload_id =
urlencoding_mode = normal
use_http_expect = False
use_https = False
use_mime_magic = True
verbosity = WARNING
website_endpoint = http://%(bucket)s.s3-website-%(location)s.amazonaws.com/
website_error =
website_index = index.html

#### 列出所有buckets
##### s3cmd ls
2024-08-27 03:19  s3://new-bucket-test
