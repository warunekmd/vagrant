# vagrant
Vagrant project

sudo apt-get install vagrant

#Uninstall old
sudo apt-get remove docker docker-engine docker.io containerd runc

#Setup repository
sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

#Add Docker’s official GPG key
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg


echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

#Install latest version
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

#Make sure Docker runs without sudo command
sudo groupadd docker

sudo usermod -aG docker $USER

#Activate changes
newgrp docker

