# Springboot Management

## How to persist data from your database container

    - `docker volume create mysqlvol`

## How to manage a mysql database using docker

    - `docker run --name mysql-server-name \
        -p 3306:3306 \
        -e MYSQL_ROOT_PASSWORD=password \
        --mount source=mysqlvol,target=/var/lib/mysql \
        -d mysql`

## Using bind mount to keep data from container

- Create folder in your local PC
  `mkdir mysql_bind_folder`

- Create a container bound to this folder
  - `docker run --name mysql-wbind \
      -p 3306:3306 \
      -e MYSQL_ROOT_PASSWORD=adminpassword \
      --mount  
      type=bind,source="$(pwd)"/mysql_bind_folder,target=/var/lib/mysql -d mysql` 