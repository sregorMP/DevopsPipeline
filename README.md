# Prerequisites

* 1 instance Jenkins Server 
* 1 instance Ansible Server
* 3 instances Swarm Server (1 Manager, 2 Workers) 
(This example i'm using centos)

![PipelineExample](https://github.com/sregorMP/DevopsPipeline/blob/master/pipe.png)

# Configuration Commons Servers
## Install Docker and git 
```
curl -fsSL https://get.docker.com | bash

systemctl enable docker && \
systemctl start docker

yum install git -y 
```
## Add User Devops and included in groups wheel,docker
```
 adduser -p mypassword devopsuser

 usermod -aG wheel,docker devopsuser
 
```
## Uncomment line /etc/sudoers 
```
 %wheel	ALL=(ALL)	NOPASSWD: ALL
```
## Go to Ansible > Docker > Jenkins folder in this sequence  to instructions of servers configurations 








