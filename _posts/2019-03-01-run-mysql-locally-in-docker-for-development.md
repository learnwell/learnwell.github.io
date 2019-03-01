---

layout: postMod1
title: Deploy MySql in 60 seconds 
author: pulkit
last_modified_at: February 27, 2019
tags: [mysql,docker,dev,devlopment,local]

---

## Goal

Run MySql locally in Docker for development

## Steps

```
# make a directory your local user's MySql needs
mkdir -p ~/apps/mysql/

# go to the directory for MySql
cd ~/apps/mysql/

# create a `docker-compose.yml` file
echo "
version: '3.3'
services:
  mysql:
    image: mysql:5.7
    container_name: mysql
    hostname: mysql
    environment:
      MYSQL_DATABASE: 'db'
      # So you don't have to use root, but you can if you like
      MYSQL_USER: 'user'
      # You can use whatever password you like
      MYSQL_PASSWORD: 'userPassword'
      # Password for root access
      MYSQL_ROOT_PASSWORD: 'rootPassword'
    ports:
      # <Port exposed> : < MySQL Port running inside container>
      - '3306:3306'
    expose:
      # Opens port 3306 on the container
      - '3306'
    volumes:
      - './volume/mysql:/var/lib/mysql'
    tty: true
" >> docker-compose.yml

# launch mysql in detached mode
docker-compose up -d

# follow logs as needed
docker-compose logs --follow mysql
```

## References

Credit where credit is due, I used these for reference:
* https://medium.com/@chrischuck35/how-to-create-a-mysql-instance-with-docker-compose-1598f3cc1bee
* https://www.masterzendframework.com/docker-development-environment/

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwMzk2MTA3NywxNDg1NjY0MTA0LC02OD
MwOTYyOTVdfQ==
-->