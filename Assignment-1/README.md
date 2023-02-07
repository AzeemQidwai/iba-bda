# CSE668 - Big Data Analytics - Assignment 1
## Running Mac-OS inside a Docker container on Ubuntu 22.04.01 LTS

![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![macOS](https://img.shields.io/badge/mac%20os-000000?style=for-the-badge&logo=macos&logoColor=F0F0F0)


### 💻 System Specifications

  + **Processor:** Intel(R) Core(TM) i3-4010U CPU @ 1.70GHz
  + **RAM:** 8GB DDR3 1600MHz
  + **OS:** Ubuntu 22.04.01 LTS

### 🐋 Docker Installation
  Follow below mentioned steps to install Docker on Ubuntu.
  1. Enable installation via HTTPS
  ```bash
    sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
  ```
  2. Add the official Docker GPG key
  ```
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  ```
  3. Add the Docker repository
  ```
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
  ```
  4. Install Docker
  ```
    sudo apt install docker-ce docker-ce-cli containerd.io
  ```
  
### ⚙️ Setting up Docker on Ubuntu
  1. Run docker without sudo
  ```
    sudo groupadd docker
  ```
  2. Add user name to the group `docker`
  ```
    sudo usermod -aG docker $USER
  ```
  3. Verify docker installation by running a sample container
  ```
    docker run hello-world
  ```
   + **Output**
      
      ![hello-wordl](https://github.com/AzeemQidwai/iba-bda/blob/main/Assignment-1/images/hello-world.png)
  4. Run Docker at each boot
  ```
    sudo systemctl enable docker
  ```
 ***
## 📀 Running Mac OS Docker Container
  This is done using sickcodes Docker-OSX. [link](https://github.com/sickcodes/Docker-OSX)
  
  ### Catalina
  Following code is used to run and create the container.
  ```
  docker run -it \
    --device /dev/kvm \
    -p 50922:10022 \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e "DISPLAY=${DISPLAY:-:0.0}" \
    sickcodes/docker-osx:latest
  ```
  
  After Installation
  
  ### Memory Usage using `htop`
  
  ![memory-usage](https://github.com/AzeemQidwai/iba-bda/blob/main/Assignment-1/images/memory-usage.png)
  
