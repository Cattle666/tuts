# Commands  
```
sudo systemctl [start,stop,restart,status] q3@ioquake  
sudo systemctl [start,stop,restart,status] q3@ioquake2  
sudo systemctl [start,stop,restart,status] q3@ioquake3  
sudo journalctl [-u,-fu] q3@ioquake  
sudo journalctl [-u,-fu] q3@ioquake2  
sudo journalctl [-u,-fu] q3@ioquake3  
```
# Configs  
```
vim /opt/ioquake/ioquake3.conf  
vim /opt/ioquake2/ioquake3.conf  
vim /opt/ioquake3/ioquake3.conf  
```
### Mod Configs  
```
cd /opt/ioquake[,2,3]/.q3a/baseq3/   
cd /opt/ioquake[,2,3]/.q3a/generations/  
cd /opt/ioquake[,2,3]/.q3a/missionpack/  
```
# Game Files  
```
cd /usr/local/games/ioquake3/  
```
# RCON  
```
quake3-rcon 192.168.88.99 dinobytes222 27960  
quake3-rcon 192.168.88.99 dindoos667 27961  
quake3-rcon 192.168.88.99 dinobytes222 27962  
```