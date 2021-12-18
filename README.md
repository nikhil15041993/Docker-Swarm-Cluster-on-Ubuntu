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
 
 docker-machine create --driver virtualbox worker1
 
 docker-machine create --driver virtualbox worker2
 ```

## Step 4 :  Check machine created successfully

```   
    docker-machine ls
    docker-machine ip manager1
```    

## Step 5 :  SSH (connect) to docker machine

```
docker-machine ssh manager1
```

## Step 6 :  Initialize Docker Swarm  

```
docker swarm init --advertise-addr MANAGER_IP
```

## Step 7 :  Join workers in the swarm

```
 docker swarm join-token worker
```
This will give command to join swarm as worker
SSH into worker node (machine) and run command to join swarm as worker

Type ``` docker info ``` to get all the details about cluster

## Step 7 :  Run containers on Docker Swarm

```
docker service create --replicas 3 -p 80:80 --name serviceName nginx
```

```
Check the status:

docker service ls
docker service ps serviceName
```
### Check on the browser by giving ip for all nodes
