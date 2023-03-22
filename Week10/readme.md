# Install jenkins, docker, docker-compose, and git 

1. Open the install.sh file with your preferred text editor (e.g., nano, vim, or gedit):

```
nano install.sh

```

2. Add the following content to install.sh:

```
#!/bin/bash

# Update packages and install prerequisite packages
sudo apt update
sudo apt upgrade -y
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# Install Git
sudo apt install -y git

# Install Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io

# Enable and start Docker service
sudo systemctl enable docker
sudo systemctl start docker

# Add the current user to the Docker group
sudo usermod -aG docker $USER
sudo groupadd docker

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Install Java
sudo apt install -y openjdk-11-jdk

# Install Jenkins
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install -y jenkins

# Enable and start Jenkins service
sudo systemctl enable jenkins
sudo systemctl start jenkins

 
 
 # 3.Adds the user "jenkins" to the "docker" group, which allows the user to run Docker #commands without needing to use sudo.
 
 sudo usermod -aG docker jenkins


```

## 4.Save and close the file.

```
Ctrl+X, then Y, then Enter.
```


## 5.Run the install.sh script:

```
./install.sh

```

## 6. Access Jenkins by opening a web browser and navigating to

```
http://<your_instance_ip>:8080
```