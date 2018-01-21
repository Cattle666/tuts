### QEMU TUT  
##### virt-install  
usage: virt-install --name NAME --ram RAM STORAGE INSTALL [options]  
--connect --> Connect to a non-default hypervisor qemu:///system for root, qemu:///session for non-root  
--virt-type --> The hypervisor on which to install the guest. Choices are kvm, qemu, xen, or kqemu  
--os-type --> Type of operating system to be used  
--name --> Name to be used for VM  
--ram --> How much ram to be used (mb)  
--disk --> Location of file system to be used by VM  
--graphics --> TYPE,opt1=arg1,opt2=arg2,...  
--video & --channel --> used for spice compatibility  
--cdrom -->  File or device to use a virtual CD-ROM device  
--vcpus --> Number of virtual processors to configure for the guest  
##### Examples:  
```bash
sudo virt-install --connect qemu:///system --virt-type kvm --os-type=linux --name mediavm --ram 4096 --disk path=/dev/bubble_raid5_vg/media --graphics spice --video qxl --channel spicevmc --cdrom /home/miles/ubuntu-16.04.2-server-amd64.iso --vcpus 4  
```
sudo virt-install --connect qemu:///system --virt-type kvm \  
--os-type=linux --name mediavm --ram 4096 --disk path=/dev/some_vg/some_lv \  
--graphics spice --video qxl --channel spicevmc \  
--cdrom /path/to/dir/ubuntu-16.04.2-server-amd64.iso --vcpus 4  
##### --Add a disk--  
cd /place/for/img  
```bash
qemu-img create -f raw example-vm-swap.img 1G
virsh attach-disk example-vm --source /place/for/img/example-vm-swap.img --target vdb --persistent  
```
mount vm side  
```bash
cfdisk /dev/sdb  
mkfs.xfs -f /dev/sdb1  
```