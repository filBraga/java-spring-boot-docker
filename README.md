# java-spring-boot-docker

# 1 - spring initializr

https://start.spring.io/

Project - Maven
Language - Java
Spring Boot - 3.4.0

Project Metadata

Group - com.filipe

Artifact -

Name - filipe

Description - Demo project for Spring Boot

Package name - com.filipe

Packaging - War

Java - 17

# 2 - jenkins

https://www.jenkins.io/doc/tutorials/tutorial-for-installing-jenkins-on-AWS/

```bash
sudo yum update
```

```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

```bash
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```

```bash
sudo yum upgrade
```

```bash
sudo yum install java-17-amazon-corretto -y
```

```bash
sudo yum install jenkins -y
```

```bash
sudo systemctl enable jenkins
```

```bash
sudo systemctl start jenkins
```

```bash
sudo systemctl status jenkins
```

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

# 3 - install git

```bash
sudo yum install git -y
```

# 4 - install docker

```bash
sudo yum install -y docker
```

```bash
sudo service docker start
```

```bash
sudo usermod -aG docker jenkins
```

```bash
sudo service jenkins restart
```

# 5 - jenkins plugin

Install Sugested Plugins

- Docker

# 6 - jenkins tools

Add the following tools:

Name: Default
Tool: git

Name: Default
Tool: maven
Install: Automatically 3.9.9

Name: Default
Tool: docker
Install: Automatically from docker.com @latest

# 7 - running local

### with mvn

```bash
mvn spring-boot:run
```

### or build

```bash
mvn clean compile
```

```bash
mvn package
```

### and run docker

```bash
docker build -f Dockerfile -t webapp .
```

```bash
docker rm -f "webappcontainer" || true
```

```bash
docker run --name "webappcontainer" -p 9090:8080 --detach webapp:latest
```
