# Install Docker on Linux
Update apt
```bash
sudo apt update
```

Upgrade apt
```bash
sudo apt upgrade
```

If the kernel upgrades, reboot the system
```bash
sudo reboot
```
Allow apt to user a repository over HTTPS
```bash
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

Add Docker's official GPG key
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
Set up the stable repository
```bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Install docker
```bash
 sudo apt update
 sudo apt install docker-ce docker-ce-cli containerd.io
```

Verify that docker is working properly
```bash
sudo docker run hello-world
```

Add your user to the docker user group (so we dont need root user or sudo)
```bash
sudo usermod -a -G docker $USER
```

For Ubuntu 20.04, this is it! Log out and log back in and you should be good to
go!


## References
[Docker documentation for Linux installation](https://docs.docker.com/engine/install/ubuntu/)

## Tags
#docker #linux #containers
