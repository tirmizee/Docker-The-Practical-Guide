### Run images

    docker run --name mysql-standalone -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -e MYSQL_DATABASE=schema -d mysql
    
### Volume

    docker volume ls
    
### Workbench

    ALTER USER root IDENTIFIED WITH mysql_native_password BY 'root';
