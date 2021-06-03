
### run images

    docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=password -e POSTGRES_USER=root -e POSTGRES_DB=docker -d postgres

### volume

    version: '3.1'

    services: 
       postgres-db:
          image: postgres
          environment: 
             POSTGRES_USER: root
             POSTGRES_PASSWORD: password
             POSTGRES_DB: jobdb
          volumes: 
             - postgres-data:/var/lib/postgresql/data

    volumes:
       postgres-data:
          driver: local
