### Run images

    docker run --name mysql-standalone -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -d mysql
