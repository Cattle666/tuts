### GLUSTERFS
###### --Initial Install--
create 3 VMs with Fedora27  
create a partition sdb1 on logical volume before OS install  
or  
add a disk using virsh  
```
cd /place/for/img  
qemu-img create -f raw example-vm-swap.img 1G  
virsh attach-disk example-vm --source /place/for/img/example-vm-swap.img --target vdb --persistent  
mount vm side  
cfdisk /dev/sdb  
mkfs.xfs -f /dev/sdb1  
mount /dev/sdb1 /data/brick1  
install glusterfs-server on all nodes and clients  
sudo systemctl start glusterd  
```
###### --IP Tables--  
```
pdsh -w server[1-3] sudo iptables -I INPUT -m state --state NEW -m tcp -p tcp --dport 24007:24008 -j ACCEPT  
pdsh -w server[1-3] sudo iptables -I INPUT -m state --state NEW -m tcp -p tcp --dport 49152:49156 -j ACCEPT  
iptables -I INPUT -p all -s <ip-address> -j ACCEPT  
```
###### --connect to peers--  
```
sudo gluster peer probe server1  
sudo gluster peer probe server2  
sudo gluster peer probe server3  
```
on each node...  
```
mkdir -p /data/brick1/gv0  
```
###### --create volume--  
```
sudo gluster volume create wads replica 3 192.168.122.205:/data/brick1/gv0 192.168.122.150:/data/brick1/gv0 192.168.122.109:/data/brick1/gv0 force  
gluster volume start gv0  
gluster volume status  
gluster volume info  
```
###### --client connection--  
```
mount -t glusterfs server1:/gv0 /mnt  
```