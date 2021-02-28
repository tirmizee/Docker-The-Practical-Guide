# Docker-The-Practical-Guide

<p align="center">
  <img src="https://docs.docker.com/engine/images/architecture.svg" width="500">
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

### Docker machine for Windown

- เชคสถานะการทำงาน

      docker-machine status

- ดู IP Address 

      docker-machine ip


