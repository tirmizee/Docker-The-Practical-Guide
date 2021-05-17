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

### template yml

```yml

version: '3.1' # หากไม่ระบุจะมีค่าเริ่มต้นเป็น version 1

services: # containers
   servicename: # ชื่อที่จำง่าย ชื่อ DNS ภายใน network เหมือนกับ --name ใน docker run 
      image: # optional ถ้าไม่ใช้ build
      command: # optional แทนที่ CMD เริ่มต้นที่ระบุโดย Image
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
