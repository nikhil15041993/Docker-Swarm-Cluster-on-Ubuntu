# Docker-Swarm-Cluster-on-Ubuntu

## Step 1 Install Docker Machine

```

curl -L https://github.com/docker/machine/releases/download/v0.16.2/docker-machine-`uname -s`-`uname -m` >/tmp/docker-machine &&
    chmod +x /tmp/docker-machine &&
    sudo cp /tmp/docker-machine /usr/local/bin/docker-machine
  ```
    
## step 2  install VirtualBox    

```
sudo apt-get install virtualbox
```

## Step 3 :  Create Docker machines

```
 docker-machine create --driver virtualbox manager1
 ```
