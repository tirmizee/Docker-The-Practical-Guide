
### Docker network default

- ##### แต่ละคอนเทนเนอร์เชื่อมต่อกับเครือข่ายเสมือนส่วนตัว "bridge"
- ##### เครือข่ายเสมือนแต่ละเครือข่ายจะกำหนดเส้นทางผ่านไฟร์วอลล์ NAT บน IP ของโฮสต์
- ##### คอนเทนเนอร์ทั้งหมดบนเครือข่ายเสมือนสามารถพูดคุยกันได้โดยไม่ต้อง -p
- ##### วิธีปฏิบัติที่ดีคือสร้าง virtual network สำหรับแต่ล่ะ app
  - #### network "web-app" สำหรับคอนเทนเนอร์ mysql และ php
  - #### network "web-api" สำหรับคอนเทนเนอร์ mongo และ node 
- ##### คอนเทนเนอร์สามารถมี virtual network ได้มากกว่า 1 หรือไม่มีเลย
- ##### skip virtual network ใช้ Host IP(--net=host)

#### Network : DNS

- คอนเทนเนอร์ไม่ควรพึ่งพา IP ในการสื่อสาร
- DNS เป็นมาตรฐานสำหรับวิธีการสื่อสารระหว่างคอนเทนเนอร์ในโฮสต์เดียวกันและข้ามโฮสต์

#### Network driver

- bridge 
- overlay 
- host

#### Network driver overview


- bridge เป็น network driver เริ่มต้นหากไม่ได้ระบุ driver อย่างชัดเจน bridge มักจะใช้เมื่อแอปพลิเคชันทำงานในคอนเทนเนอร์แบบสแตนด์อโลนที่จำเป็นต้องสื่อสารระหว่างกัน.
- overlay 
- host


### Docker network commands

Show network 

    docker network ls

Inspect a network 

    docker network inspect <network>

Create a network

    docker network create --driver //ไม่จำเป็นต้องใช้ --driver default คือ bridge

Attach a network to container 

    docker network connect <network> <container>
    
Detach a network from contaner 

    docker network disconnect <network> <container>

#### flag

- attachable คอนเทนเนอร์ที่อยู่นอกบริการ Swarm สามารถเข้าถึงเครือข่ายได้

#### Reference

- https://medium.com/readmoreth/docker-connect-database-timeout-b23f781dcff7#:~:text=%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B9%80%E0%B8%A0%E0%B8%97%E0%B8%82%E0%B8%AD%E0%B8%87%20Docker%20Network&text=Bridge%20%E0%B8%84%E0%B8%B7%E0%B8%AD%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%A3%E0%B8%B1%E0%B8%99%20container,Gateway%20%E0%B9%80%E0%B8%9B%E0%B9%87%E0%B8%99%E0%B8%82%E0%B8%AD%E0%B8%87%E0%B8%95%E0%B8%B1%E0%B8%A7%E0%B9%80%E0%B8%AD%E0%B8%87
- https://docs.docker.com/network/
