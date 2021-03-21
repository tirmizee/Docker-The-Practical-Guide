# Docker-The-Practical-Guide

<p align="center">
  <img src="https://docs.docker.com/engine/images/architecture.svg" width="600">
</p>



- การดู version docker

      docker -v

- การดู iamges ที่มีทั้งหมด

      docker images

- การดูวันที่ของ container 

      docker exec -it container-id date
      
- การ Time Zone ของ container 

      docker exec -it container-id cat /etc/timezone
      
- การดู Log ของ container 

      docker logs container-id

Ref : https://docs.docker.com/engine/reference/commandline/logs/

### Ref

- https://damrongs.medium.com/%E0%B8%97%E0%B8%B3%E0%B9%83%E0%B8%AB%E0%B9%89-docker-%E0%B9%80%E0%B8%82%E0%B9%89%E0%B8%B2%E0%B8%96%E0%B8%B6%E0%B8%87-insecure-registry-a773052f2b74
