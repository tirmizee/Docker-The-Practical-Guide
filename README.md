# Docker-The-Practical-Guide

- การดู version docker

      docker -v

- การดู iamges ที่มีทั้งหมด

      docker images

- การดูวันที่ของ container 

      docker exec -it container-id date
      
- การ Time Zone ของ container 

      docker exec -it container-id cat /etc/timezone
