# Configuration Jenkins Server
## Clone this repositore 
```
 git clone https://github.com/sregorMP/DevopsPipeline.git
```
## Run command docker to create image jenkins with apache-maven
```
 cd ./DevopsPipeline/jenkins && \
 docker build -t myjenkins:v1.0 . 
```
## Run command docker to create container jenkins
```
docker container run -d --name myJenkins -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home myjenkins:v1.0 
```

## Initial Password Jenkins
```
docker exec -ti myJenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

## Setup maven, git and publish over ssh on jenkins

### Install maven, github and publish overssh plugins

`Manage Jenkins`  > `Jenkins Plugins` > `available` > `Maven Invoker |  Maven Integration | github | Publish Over SSH `

### Configure Maven Path

`Manage Jenkins` > `Global Tool Configuration` > `Maven` > `Input: /opt/maven/apache-maven`

### Configure SSH ansible server 
## Don't forget of check use password autentication and configure

`Manage Jenkins` > `Configure System` > `SSH Servers` 

### New Job

`New item`  > `Input name ` > `Select Maven Project` > `OK`

### Configuration Job

`Go to Source Code Management`  > `Select Git` > `Repository URL` > `Input: https://github.com/sregorMP/HelloWorldMavenJavaWeb.git `

`Build Triggers`  > `Select Pool SCM` > `Type: * * * * * `

`Build`  > `Goals and options` > `Type: clean install package` 

### Post-build Actions

`Send build artifacts over SSH` > `Select Ansible Server` 

`Source files` > `Input: **/*.war `

`Remove Prefix` > `Input: webapp/target `

`Remote directory` > `Input: //home//devopsuser//DevopsPipeline`

`Exec Command` > `Input: cd //home//devopsuser//DevopsPipeline//ansible ; ansible-playbook -i hosts devops-image.yml ; ansible-playbook -i hosts devops-pipeline.yml`

# YEAHHHHH PIPELINE SUCCESS access http://ipswarm:8080/webapp/
