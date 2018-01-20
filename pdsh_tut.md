### Remote Cluster Management with pdsh & dshbak 
##### pdsh  
pdsh is a parallel remote shell client  
```
pdsh -w node[001-100] <some-command> | dshbak -c  
```  
example when greping for a specific string:  
```
pdsh -w node[001-100] grep 'string' /var/log/messages | dshbak -c  
```
-w		Create target host list  
-x		exclude target hosts  
hostname and range = hostname[num- thru num+]  
or  
hostname and range = hostnamea,hostnamed,hostnamex  
single string, no spaces  
##### dshbak  
dshbak is a program that formats pdsh output into human form  

-c		Do not display identical output from nodes twice.  
		Instead, print the list of nodes with matching output in the header block  
-d DIR	Write consolidated node output to separate files in output directory DIR  
-f		With -d, force creation of specified DIR  
#####--set hostnames--  
```
hostnamectl set-hostname server1  
```
##### --set host list--  
vim /etc/hosts  
```
192.168.1.1 server1  
192.168.1.2 server2  
192.168.1.3 server3  
~  
~  
~  
```
##### --config pdsh-rcmd-ssh(Ubuntu specific)--  
``` 
sudo vim .bashrc  
```
add this to the end of the file  
```
#pdsh-rcmd fix
export PDSH_RCMD_TYPE=ssh  
```
or  
```
cat .bashrc >> export PDSH_RCMD_TYPE=ssh
```