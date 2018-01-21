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
vim /etc/sysconfig/network-scripts/ifcfg-{adapter}
```
TYPE=Ethernet  
PROXY_METHOD=none  
BROWSER_ONLY=no  
BOOTPROTO=none  
IPADDR=192.168.122.205  
DEFROUTE=yes  
IPV4_FAILURE_FATAL=no  
IPV6INIT=yes  
IPV6_AUTOCONF=yes  
IPV6_DEFROUTE=yes  
IPV6_FAILURE_FATAL=no  
IPV6_ADDR_GEN_MODE=stable-privacy  
NAME=ens3  
UUID=00000000-asdf-asdf-asdf-123456789asd  
ONBOOT=yes  
AUTOCONNECT_PRIORITY=-999  
DEVICE=ens3  
ZONE=FedoraServer  
~  
~  
~    
```
ifconfig --> depreciated  
An easy way to see what processes own which network connections:  
```
sudo netstat -tup  
```
for connections and  
```
sudo netstat -tupl  
```
for listening process  
```
sudo netstat -tulpen
```