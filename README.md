# Docker-The-Practical-Guide

<p align="center">
  <img src="https://docs.docker.com/engine/images/architecture.svg" width="600">
</p>



- การดู version docker

      docker -v

- การดู iamges ที่มีทั้งหมด

      docker images

- แสดงรายการคอนเทนเนอร์ที่กำลังทำงานอยู่และคอนเทนเนอร์ที่หยุดทำงาน

      docker ps -a

- สร้างอิมเมจจาก Dockerfile ในไดเร็กทอรีปัจจุบัน

      #เพิ่ม -t เพื่อระบุชื่อ tag
      docker build -t shykes/myapp .
      
      #เพิ่ม -f เพื่อชี้ไปที่ Dockerfile ที่ใดก็ได้ในระบบไฟล์ของคุณ
      docker build -f /path/to/a/Dockerfile . 

- การดูวันที่ของ container 

      docker exec -it container-id date

- แสดงการแมปพอร์ต (หรือเฉพาะ) สำหรับ container

      docker port [CONTAINER]

- แสดงกระบวนการทำงานใน container

      docker top [CONTAINER]

- สดงสถิติการใช้ทรัพยากรแบบสดของ

      docker stats [CONTAINER]
      
- รัน command ใน container ที่กำลังทำงาน

      docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

      docker exec -it ubuntu_bash bash

- การดู Time Zone ของ container 

      docker exec -it container-id cat /etc/timezone
      
- การดู Log ของ container 

      docker logs container-id
      
- container restrt (no, on-failure, unless-stopped, always)

      docker run -d --restart always redis
      
      docker run -d --restart on-failure:5 testing_restarts

Ref : https://docs.docker.com/engine/reference/commandline/logs/

### Ref

- https://damrongs.medium.com/%E0%B8%97%E0%B8%B3%E0%B9%83%E0%B8%AB%E0%B9%89-docker-%E0%B9%80%E0%B8%82%E0%B9%89%E0%B8%B2%E0%B8%96%E0%B8%B6%E0%B8%87-insecure-registry-a773052f2b74
- https://www.youtube.com/watch?v=pTFZFxd4hOI
- https://phoenixnap.com/kb/list-of-docker-commands-cheat-sheet
