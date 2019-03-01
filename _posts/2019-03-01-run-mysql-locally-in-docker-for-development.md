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
version: '3'
services:
  mysql:
    image: mysql:5.7
    volumes:
      - './volume/mysql:/var/lib/mysql'
    container_name: mysql
    hostname: mysql
    environment:
      - MYSQL_ROOT_PASSWORD=your_secret_password
    tty: true
" >> docker-compose.yml

# launch mysql in detached mode
docker-compose up -d

# follow logs as needed
docker-compose logs --follow mysql
```

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ4NTY2NDEwNCwtNjgzMDk2Mjk1XX0=
-->