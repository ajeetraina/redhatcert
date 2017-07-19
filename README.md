
# How to run Red Hat Certification Test Suite Inside Docker container

# On Test Manager:


## Install Docker 17.05 Enterprise Edition on Red Hat Enterprise Linux 7.3

- Register to Docker Store. In case you have DockerHub ID, login through the same credential.

 - Browse to Docker Store - https://store.docker.com/editions/enterprise/docker-ee-server-rhel
 
 - Follow the steps under https://docs.docker.com/engine/installation/linux/docker-ee/rhel/
 
 - Or you can directly add docker-ee.repo( from the repository) under /etc/yum.repos.d/ & and then run the below command:
 
 ```yum update```
 
 
 ```yum install docker-ee```
 
 ## Start the Docker Daemon
 
```systemctl restart docker```

## verify if Docker is up and running

```docker version```

```docker info```


## Pulling Docker Image for Red Hat certification Suite 

```docker pull ajeetraina/redhatcert```

## Running Docker Container

```docker run --privileged --net=host -ti -e container=docker -v /sys/fs/cgroup:/sys/fs/cgroup ajeetraina/redhatcert /usr/sbin/init```

Keep the terminal open. Open up the new terminal and follow the next step:

### Running the HWCERT Service

```docker exec -it <container-id> rhcert-backend server start```

## Ensure that rhcert services are up and running using the below command in new terminal

```docker exec -it <container-id> rhcert-backend server status```


# On System Under Test:


## Install Docker 17.05 Enterprise Edition on Red Hat Enterprise Linux 7.3

- Register to Docker Store. In case you have DockerHub ID, login through the same credential.

 - Browse to Docker Store - https://store.docker.com/editions/enterprise/docker-ee-server-rhel
 
 - Follow the steps under https://docs.docker.com/engine/installation/linux/docker-ee/rhel/
 
 - Or you can directly add docker-ee.repo( from the repository) under /etc/yum.repos.d/ & and then run the below command:
 
 ```yum update```
 
 
 ```yum install docker-ee```
 
 ## Start the Docker Daemon
 
```systemctl restart docker```

## verify if Docker is up and running

```docker version```

```docker info```


## Pulling Docker Image for Red Hat certification Suite 

```docker pull ajeetraina/redhatcert```

## Running Docker Container

```docker run --privileged --net=host -ti -e container=docker -v /sys/fs/cgroup:/sys/fs/cgroup ajeetraina/redhatcert /usr/sbin/init```

Keep the terminal open. Open up the new terminal and follow the next step:

### Running the HWCERT Service

```docker exec -it <container-id> rhcert-backend server start```

## Ensure that rhcert services are up and running using the below command in new terminal

```docker exec -it <container-id> rhcert-backend server status```


 
 
