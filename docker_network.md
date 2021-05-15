
### Docker network default

- ##### แต่ละคอนเทนเนอร์เชื่อมต่อกับเครือข่ายเสมือนส่วนตัว "bridge"
- ##### เครือข่ายเสมือนแต่ละเครือข่ายจะกำหนดเส้นทางผ่านไฟร์วอลล์ NAT บน IP ของโฮสต์
- ##### คอนเทนเนอร์ทั้งหมดบนเครือข่ายเสมือนสามารถพูดคุยกันได้โดยไม่ต้อง -p
- ##### วิธีปฏิบัติที่ดีคือสร้าง virtual network สำหรับแต่ล่ะ app
  - #### network "web-app" สำหรับคอนเทนเนอร์ mysql และ php
  - #### network "web-api" สำหรับคอนเทนเนอร์ mongo และ node 
- ##### คอนเทนเนอร์สามารถมี virtual network ได้มากกว่า 1 หรือไม่มีเลย
- ##### skip virtual network ใช้ Host IP(--net=host)

#### Default security

- คอนเทนเนอร์ของแอปมารวมไว้ในเครือข่ายเดียว
- เปิดเผยพอร์ตบนโฮสต์ใช้โดยเฉพาะเท่านั้น

#### Network : DNS

- คอนเทนเนอร์ไม่ควรพึ่งพา IP ในการสื่อสาร
- DNS เป็นมาตรฐานสำหรับวิธีการสื่อสารระหว่างคอนเทนเนอร์ในโฮสต์เดียวกันและข้ามโฮสต์

### Docker network commands

Show network 

    docker network ls

Inspect a network 

    docker network inspect <network>

Create a network

    docker network create --driver //ไม่จำเป็นต้องใช้ --driver

Attach a network to container 

    docker network connect <network> <container>
    
Detach a network from contaner 

    docker network disconnect <network> <container>
