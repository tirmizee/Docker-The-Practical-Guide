### Run

      docker run --name maria-standalone -p 3306:3306 -e MARIADB_ROOT_PASSWORD=root -e MARIADB_USER=user -e MARIADB_PASSWORD=pass -e MARIADB_DATABASE=test -d mariadb
