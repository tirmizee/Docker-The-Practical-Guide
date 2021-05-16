### Run images

    docker run --name mysql-standalone -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -e MYSQL_DATABASE=schema -d mysql
    
### Volume

    docker volume ls
    
    docker run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True -v mysql-db:/var/lib/mysql  mysql
    
### Workbench

    ALTER USER root IDENTIFIED WITH mysql_native_password BY 'root';
