### Git Tut  
Git is a version control system  
###### Authentication  
```
ssh-keygen.exe -t rsa -b 4096 -C miles@WorkStudyPC-2017-02-12  
```
or  
```
ssh-keygen -t rsa -b 4096 -C miles@WorkStudyPC-2017-02-12
```
```
git config --global user.email "akthunderfolk@gmail.com"  
git config --global user.name "Miles Lowroad"  
```
###### Cloning and Setting Repos  
```
git clone git@github.com:ZedekThePD/odinbot.git  
git remote  
git remote -v  
git remote set --help  
git remote set-url origin git@github.com:ValhallaGamePlays/odinbot.git      git@github.com:ZedekThePD/odinbot.git  
```
###### Making Changes  
```
git add .    
```
or  
```
git add -A  
```
or  
```
git add git@github.com:ValhallaGamePlays/VGP-Invasion.git  
```
```
git commit -m "Initial commit"  
git push  
```
###### General Administration  
```
git status  
git log  
git diff  
```