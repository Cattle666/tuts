### virsh  
The virsh program is the main interface for managing virsh guest domains  
It currently supports Xen, QEmu, KVM , LXC , OpenVZ, VirtualBox and VMware ESX  
##### --See what's going on--  
virsh list --all  
  
list  
	--inactive | list inactive domains  
	--all | list inactive and active domains  
	--transient | list transient domains  
	--persistent | list persistent domains  
	--with-snapshot | list domains with existing snapshot  
	--without-snapshot | list domains without snapshot  
	--state-running | list domains in running state   
	--state-paused | list domains in paused state  
	--state-shutoff | list domains in shutoff state  
	--state-other | list domains in other states  
	--autostart | list domains with autostart enabled  
	--no-autostart | list domains with autostart   
	--with-managed-save | list domains with managed save state  
	--without-managed-save | list domains without managed save  
	--uuid | list uuid's only  
	--name | list domain names only  
	--table | list table (default)  
	--managed-save | mark inactive domains with managed save state  
	--title | show domain title  
##### --Make changes--
virsh edit {guest_name}  
    <graphics type='spice' port='5900' autoport='no' listen='0.0.0.0'>  
      <listen type='address' address='0.0.0.0'/>  
##### --Start and stop domain  
virsh destroy {guest_name}  
virsh start {guest_name}  
 ##### --Deleting a domain--  
virsh dumpxml --domain fedoravm2 | grep 'source file'
virsh destroy fedoravm2
virsh undefine fedoravm2