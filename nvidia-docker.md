# Install Docker-CE so it works with nvidia-docker 20190112

  https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-using-the-repository
  
    sudo apt-get remove docker docker-engine docker.io # Ubunto default is no good for nvidia-docker

    sudo apt-get update

    sudo apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - 

    sudo add-apt-repository \
      "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
      $(lsb_release -cs) \
      stable"

    sudo apt-get update

    sudo apt-get install docker-ce                                 #<----------- gives the latest .....

    sudo apt-get install docker-ce=5:18.09.0~3-0~ubuntu-bionic     #<----------- latest did not work, downgraded; 20190112

    sudo docker container run hello-world  # TEST installation

## Manage Docker as a non-root user

    sudo groupadd docker

    sudo usermod -aG docker $USER

## Verify that you can run docker commands *without* sudo.

    docker run hello-world

## Configure Docker to start on boot

    sudo systemctl enable docker

    (sudo systemctl disable docker # this will disable start on boot)


# Install Nvidia-Docker

    curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | \
      sudo apt-key add -

    distribution=$(. /etc/os-release;echo $ID$VERSION_ID)

    curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | \
      sudo tee /etc/apt/sources.list.d/nvidia-docker.list

    sudo apt-get update

## Install nvidia-docker2 and reload the Docker daemon configuration
    sudo apt-get install -y nvidia-docker2

    sudo pkill -SIGHUP dockerd

## Test nvidia-smi with the latest official CUDA image
    docker run --runtime=nvidia --rm nvidia/cuda:9.0-base nvidia-smi






