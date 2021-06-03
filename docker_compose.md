### Docker Compose

Docker Compose เป็นเครื่องมือสำหรับเรียกใช้งานแอพพลิเคชั่นหลายคอนเทนเนอร์บน Docker ที่กำหนดโดยใช้รูปแบบไฟล์ Compose.

### docker-compose.yml

- รูปแบบ Compose YAML มีเวอร์ชัน 1, 2, 2.1, 3, 3.1 หากไม่ระบุจะมีค่าเริ่มต้นคือ v1 และ version: "2" เทียบเท่ากับ version: "2.0"
- ไฟล์ YAML สามารถใช้กับคำสั่ง docker-compose
- สามารถใช้นามสกุล .yml หรือ. yaml ได้
- Compose file ต้องมีอย่างน้อย 1 คอนเทนเนอร์
- docker-compose --help
- docker-compose.yml เป็นชื่อไฟล์เริ่มต้น แต่สามารถใช้ docker-compose -f <file.yml> ซึ่งระบุไฟล์ที่ต้องการ

### docker-compose CLI

- เครื่องมือ CLI มาพร้อมกับ Docker สำหรับ Windows/Mac แต่ดาวน์โหลดแยกต่างหากสำหรับ Linux
- ไม่ใช่เครื่องมือระดับ production แต่เหมาะอย่างยิ่งสำหรับการพัฒนาและทดสอบใน local
- คำสั่งที่พบบ่อยที่สุดของ docker-compose
   - docker-compose up # setup volumes/networks and start all containers
   - docker-compose down # stop all containers and remove cont/vol/net
- หากโปรเจ็กต์ทั้งหมดมี Dockerfile และ docker-compose.yml
"การเริ่มต้นใช้งานของนักพัฒนาคนใหม่" ก็แค่ 
   - git clone github.com/some/software
   - docker-compose up

- xxx

      docker-compose up
      
- xxx

      docker-compose up -d 
      
- xxx

      docker-compose ps

- xxx

      docker-compose start [service-name]

- xxx

      docker-compose stop [service-name]
      
### volumes

- volume external หากถูกตั้งค่าเป็น true ระบุว่าไดรฟ์ข้อมูลนี้ถูกสร้างขึ้นนอก Compose ไม่พยายามสร้างและทำให้เกิดข้อผิดพลาดหากไม่มีอยู่

      volumes:
         data:
            external: true


### template yml

```yml

version: '3.1' # หากไม่ระบุจะมีค่าเริ่มต้นเป็น version 1

services: # containers
   servicename: # ชื่อที่จำง่าย ชื่อ DNS ภายใน network เหมือนกับ --name ใน docker run 
      image: # optional ถ้าไม่ใช้ build
      command: # optional แทนที่ CMD เริ่มต้นที่ระบุโดย Image
      ports: # publish port 
      networks: # optional
      environment: # optional เหมือนกับ -e ใน docker run
      volumes: # optional เหมือนกับ -v ใน docker run
   servicename2:
   
   volumes: # optional เหมือนกับ docker volume create
   networks: # optional เหมือนกับ docker network create
```

### Reference

- https://yaml.org/refcard.html
- https://yaml.org/start.html
- https://stackoverflow.com/questions/39988844/docker-compose-up-vs-docker-compose-up-build-vs-docker-compose-build-no-cach
