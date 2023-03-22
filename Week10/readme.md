# Install jenkins, docker, docker-compose, and git 

### 1. Open the install_git_docker_docker_compose.sh file :

```
nano install_git_docker_dockercompose.sh

```

### 2. Add the following content to install_git_docker_docker_compose.sh :

```
#!/bin/bash

# Update the package list
sudo apt update

# Install Git
sudo apt install git -y

# Install Docker
sudo apt install docker.io -y

# Add the current user to the Docker group
sudo usermod -aG docker ${USER}

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

# Make the Docker Compose binary executable
sudo chmod +x /usr/local/bin/docker-compose

# Enable Docker service
sudo systemctl enable docker.service

# Enable Docker Compose
sudo systemctl enable docker-compose.service


```



## 3.Save and close the file.
```
Ctrl+X, then Y, then Enter.
```



## 4. Open the install_Jenkins.sh file :

```
nano install_Jenkins.sh

```


### 5. Add the following content to install_Jenkins.sh :
```
#!/bin/bash

# Update package lists and install Java
sudo apt-get update -y
sudo apt-get install openjdk-11-jdk -y

# Add Jenkins repository and key
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

# Update package lists again and install Jenkins
sudo apt-get update -y
sudo apt-get install jenkins -y

# Start and enable Jenkins service
sudo systemctl start jenkins
sudo systemctl enable jenkins

# Print the initial admin password
echo "Initial Jenkins admin password:"
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```



## 6.Save and close the file.
```
Ctrl+X, then Y, then Enter.
```


 
## 7. Make the install.sh script executable:
```
chmod +x install_git_docker_dockercompose.sh
```

```
chmod +x install_Jenkins.sh
```


## 8 .Run the install.sh script:

```
./install_git_docker_dockercompose.sh

```


```
./install_Jenkins.sh

```

## 9.Adds the user "jenkins" to the "docker" group, which allows the user to run Docker #commands without needing to use sudo.
 
 ```
sudo usermod -aG docker $USER
sudo groupadd docker
sudo usermod -aG docker jenkins
sudo groupadd jenkins
```



## 10. Access Jenkins by opening a web browser and navigating to

```
http://<your_instance_ip>:8080
```

## 11. Initial Jenkins admin password:"

```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```