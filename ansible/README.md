# Configuration Ansible Server
## Install ansible and git
### Don't forget of alter ip in hosts files 
```
yum install ansible -y 
```

## Clone repositore on ansible server
```
git clone https://github.com/sregorMP/DevopsPipeline.git && \ 
cd DevopsPipeline/ansible
```
## Create ssh keys on ansible and swarm server
```
ssh-keygen
```

## Estabilish trust relationship between ansible and swarm
```
ssh-copy-id devopsuser@ipswarmserver
```

## Test of comunication between servers
```
ansible -m ping -i hosts web
```

## Login dockerhub with your acount
```
docker login
```
