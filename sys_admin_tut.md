### version  
cat /etc/lsb-release  
### ram  
sudo dmidecode -t memory  
free -g  
### cpu  
cat /proc/cpuinfo | grep 'model name' | uniq  
lscpu  
### disk  
lsblk  
df -h  
dmsg | tail --> list last four, useful when plugging in USB drives  
### admin/permissions  
sudo vim /etc/bash.bashrc  
### network  
ip addr  
ifconfig --> depreciated  
An easy way to see what processes own which network connections:  
```bash
sudo netstat -tup  
```
for connections and  
```bash
sudo netstat -tupl  
```
for listening process  
```bash
sudo netstat -tulpen  
```
###### ifcfg  
vim /etc/sysconfig/network-scripts/ifcfg-{adapter}  
```vim
TYPE=Ethernet  
PROXY_METHOD=none  
BROWSER_ONLY=no  
BOOTPROTO=none --> static or dhcp  
IPADDR=192.168.0.2  --> set IP Address  
DEFROUTE=yes  
IPV4_FAILURE_FATAL=no  
IPV6INIT=yes  
IPV6_AUTOCONF=yes  
IPV6_DEFROUTE=yes  
IPV6_FAILURE_FATAL=no  
IPV6_ADDR_GEN_MODE=stable-privacy  
NAME=ens3 --> name of network adapter  
UUID=00000000-asdf-asdf-asdf-123456789asd  
ONBOOT=yes  
AUTOCONNECT_PRIORITY=-999  
DEVICE=ens3    
ZONE=FedoraServer  
NETMASK=255.255.255.0  
BROADCAST=10.0.0.255  
GATEWAY=10.0.0.1  
~  
~  
~  
```