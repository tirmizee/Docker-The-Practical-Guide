
### docker swarm commands

- node คือ instance ของ Docker engine ที่เข้าร่วมใน Docker swarm. สามารถเรียกใช้ node อย่างน้อยหนึ่งโหนดบนคอมพิวเตอร์จริงเครื่องเดียวหรือเซิร์ฟเวอร์คลาวด์ แต่การใช้งาน production โดยทั่วไปจะรวมโหนด Docker ที่กระจายอยู่ในเครื่องทางกายภาพและคลาวด์หลายเครื่อง
- service
- network ที่ใช้ใน docker swrom จะมี driver เป็น overlay
##### เริ่มต้น docker swarm

      docker swarm init

##### แสดงการทำงาน node ของ docker swarm

      docker node ls

##### แสดงการทำงาน service ของ docker swarm

      docker service ls


##### สร้าง service ของ docker swarm

      docker service create alpline ping 8.8.8.8

##### แสดงการทำงาน service ที่ระบุ

      docker service ps <ID|NAME>

##### แก้ไข service ที่ระบุ โดยการเพิ่มจำนวน service

      docker service update <ID> --replicas 3 

#### Manager status 
      - Leader คือ node ตัวจัดการหลัก
      - Reachable คือ nodeผู้จัดการที่เข้าร่วม joint-manager. หากโหนดผู้นำไม่พร้อมใช้งาน โหนดนี้จะมีสิทธิ์ได้รับการเลือกตั้งเป็นผู้นำคนใหม่

#### Docker swarm cluster (Play With Doker)

- ##### สร้างเครื่อง 3 เครื่อง (node1, node2, node3, node4)

- ##### ทำการสร้าง swarm node1 เป็น manager

      เริ่มต้น mode docker swarm
      docker swarm init --advertise-addr=192.168.0.28
      
      แสดงรายการข้อมูลของ node ซึ่ง node manager เท่านั้นที่ใช้คำสั่งนี้ได้
      docker node ls
 
- ##### ทำการสร้าง swarm node2 เป็น worker node

      docker swarm join --token SWMTKN-1-5r3sdl8qx8qjzcwy54rywa62m3lt83sbyvu6mm2jej2xbpccpl-6bqbothq4pf39xsg8xl1ozjfo 192.168.0.28:2377

- ##### ทำการสร้าง swarm node3 เป็น worker node

      docker swarm join --token SWMTKN-1-5r3sdl8qx8qjzcwy54rywa62m3lt83sbyvu6mm2jej2xbpccpl-6bqbothq4pf39xsg8xl1ozjfo 192.168.0.28:2377

- ##### ทำการ update node2 ให้เป็น manager

      แก้ไข node2 จาก worker ให้เป็น manager
      docker node update --role manager node2
      
      แสดงรายการ node 
      docker node ls

- ##### ทำการ update node2 ให้เป็น worker

      แก้ไข node2 จาก manager ให้เป็น worker
      docker node update --role worker node2
      
      แสดงรายการ node 
      docker node ls

- ##### ทำการสร้าง swarm node4 เป็น manager

      run คำสั่งนี้ใน node manager ใดๆ เพื่อสร้าง token สำหรับ join manager
      docker swarm join-token manager

      run คำสั่งต่อไปนี้ใน node4 เพื่อ join manager node
      docker swarm join --token SWMTKN-1-5r3sdl8qx8qjzcwy54rywa62m3lt83sbyvu6mm2jej2xbpccpl-55di819h02d9wt3wf0bybuk7u 192.168.0.28:2377

- ##### run คำสั่งสร้าง service replicate 3 ที่ manager node ใดๆ
      
      สร้าง service จาก alpine image replicas 3 
      docker service create --replicas 3 alpine ping 8.8.8.8
      
      แสดงรายการของ service
      docker service ls
      
      แสดง tasks ของ some_service_name service
      docker service  ps some_service_name
      
### Reference

- https://stackoverflow.com/questions/49596962/what-is-the-difference-between-manager-leader-to-manager
