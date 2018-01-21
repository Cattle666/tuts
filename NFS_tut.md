##### install (Ubuntu)
server    
```bash
sudo apt install nfs-kernel-server  
```
client  
```bash
sudo apt install nfs-common
```
##### install (CentOS / rhel)  
server and client  
```bash
yum install nfs-utils nfs-utils-lib  
```
##### mount shared directory (server-side) 
vim /etc/exports  
/path/to/directory     client-IP address(options)  
example:  
```vim
username	/home/username		192.168.1.101(rw,sync,root_squash,subtree_check)  
/home/username     192.168.1.0/24(rw,sync,root_squash,subtree_check)  
~  
~  
~  
```
exportfs -ra  
##### mount nfs (client-side)  
vim /etc/fstab  
```vim
nfs-server-ip:/home/username    /mnt/nfs-share      nfs       rw,soft,intr,noatime,x-gvfs-show  
~  
~  
~  
```
mkdir /mnt/nfs-share  
mount -a  
or  
mount sdx /mnt/nfs-share  
or  
mount 192.168.122.231:/home/username /mnt/nfs-share -o rw,soft,intr,noatime,x-gvfs-show  