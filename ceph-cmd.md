###### ceph -s 或 ceph status<br>
###### ceph -v<br>
###### ceph osd df<br>
###### ceph df<br>
###### rados df<br>
###### ceph orch host ls \#列出集群中的主机
###### ceph orch ls \#列出集群中的服务
###### ceph orch ps \#列出集群中的服务、主机、进程
###### orch apply [<service_type:mon|mgr|rbd-mirror|cephfs-mirror|crash|alertmanager|grafana|node-exporter|prometheus|loki|promtail|mds|rgw|nfs|iscsi|snmp-gateway>]

###### orch daemon add [<daemon_type:mon|mgr|rbd-mirror|cephfs-mirror|crash|alertmanager|grafana|node-exporter|prometheus|loki|promtail|mds|rgw|nfs|iscsi|snmp-gateway>] 


###### ceph orch device ls

###### ceph mon dump \#查看monitor map
###### ceph fs dump \#查看MDS map

###### ceph osd dump \#查看OSD map
###### ceph osd getcrushmap -o {filename}，crushtool -d {comp-crushmap-filename} -o {decomp-crushmap-filename}，cat decomp-crushmap-filename \#查看CRUSH map
###### ceph osd tree \#获取集群 CRUSH 层次结构（包括权重）的简单视图
###### ceph osd crush rule ls \#查看集群定义的规则
###### ceph osd crush rule dump \#查看规则的内容
