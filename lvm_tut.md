# Logical Volume Manager  
lvm is a system of managing logical volumes  
##### Create physical volume  
```bash
sudo pvcreate /dev/sdb1  
```
##### Create volume group  
```bash
sudo vgcreate t610 /dev/sdb1  
```
##### Create logical volume  
```bash
sudo lvcreate -n solusvm -L 20G t610  
```
##### Make file system on logical volume  
```bash
sudo mkfs -t ext4 /dev/t610/solusvm  
```
##### Mount logical volume  
sudo mount /dev/mapper/t610/solusvm  
##### List the contents of mapper (mount points)  
```bash
ls -al /dev/mapper  
```
##### List the contents of a specific volume group  
```bash
ls -al /dev/t610/  
```
##### List all physical volumes  
```bash
sudo pvs  
```
##### List all volume groups  
```bash
sudo vgs  
```
##### List all logical volumes  
```bash
sudo lvs  
sudo lvscan  
```
##### Resize Logical volume  
```bash
sudo lvresize -L+20G /dev/t610/solusvm  
```
##### Delete a logical volume  
```bash
sudo umount /dev/t610/solusvm  
sudo lvremove /dev/t610/solusvm   
```