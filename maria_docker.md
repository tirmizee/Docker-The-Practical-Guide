### Run

      docker run --name maria-standalone -p 3306:3306 -e MARIADB_ROOT_PASSWORD=root -e MARIADB_USER=app_user -e MARIADB_PASSWORD=Password123! -e MARIADB_DATABASE=test -d mariadb
