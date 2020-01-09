---
layout: post
title: Docker Compose 
date:   2020-09-01 16:04:00 +0300
image:  dcom.png
tags:   Docker Compose 
---
What is Docker-Compose?

Docker-Compose is used to manage several containers at the same time for the same application. This tool offers the same features as Docker but allows you to have more complex applications.	

How docker-compose work?

-   use  `yaml`  files to configure application services (`docker-compose.yaml,docker-compose.yml`)
-   can start all the services with a single command (  `docker-compose up`  )
-   can stop all the service with a single command (  `docker-compose down`  )
-   able to scale up the specific services when required.
-   works in all environments: production, staging, development, testing, as well as CI workflows

**Compose file Structure**

Step1: Install Docker Compose In Linux 

                                                                                                                                                                    

	$sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
    $sudo chmod +x /usr/local/bin/docker-compose
    $docker-compose --version(check docker compose version)


Step2: Define Common Options in compose file

 - version: (compose file version)
 - services:  (web service, database service,etc..any service)
 - image: (Specify the image to start the container from. Can either be a repository/tag or a partial image ID)
 - build: (Configuration options that are applied at build time.)
 - context: (Either a path to a directory containing a Dockerfile, or a url to a git repository.)
 - command:  (override the command)
 - depends_on: (Express dependency between services, Service dependencies cause the following behaviors)
 - links: (Link to containers in another service. Either specify both the service name and a link alias)
 - volumes: (Mount host paths or named volumes, specified as sub-options to a service.)
 - environments: (This option allows you to add additional environment variables, beyond those defined in your.)
 - ports:  (Expose port number
      eg. 8800(define host):3306(mysql default host)
Futher more....

Step3:Create Docker  Compose File sample
					
	$mkdir ~/wordpressdocker && cd ~/wordpressdocker
	$vi docker-compose.yml


```
wordpress:
    image: wordpress
    links:
     - mariadb:mysql
    environment:
     - WORDPRESS_DB_PASSWORD=password
    ports:
     - "public_ip:80:80"
    volumes:
     - ./html:/var/www/html
mariadb:
    image: mariadb
    environment:
     - MYSQL_ROOT_PASSWORD=password
     - MYSQL_DATABASE=wordpress
    volumes:
     - ./database:/var/lib/mysql
```

Exit From Vim
	
	$docker-compose up -d

![enter image description here](https://miro.medium.com/max/1021/1*X98d4dsk_ymmjqnM0ne4Xg.png)

Reference learning Docker Basic

[https://tecadmin.net/tutorial/docker/docker-dockerfile/](https://tecadmin.net/tutorial/docker/docker-dockerfile/)

![]({{site.baseurl}}/img/dockercom.png)








