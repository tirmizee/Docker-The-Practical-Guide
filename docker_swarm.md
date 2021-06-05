
### docker swarm commands

- node คือ instance ของ Docker engine ที่เข้าร่วมใน Docker swarm. สามารถเรียกใช้ node อย่างน้อยหนึ่งโหนดบนคอมพิวเตอร์จริงเครื่องเดียวหรือเซิร์ฟเวอร์คลาวด์ แต่การใช้งาน production โดยทั่วไปจะรวมโหนด Docker ที่กระจายอยู่ในเครื่องทางกายภาพและคลาวด์หลายเครื่อง
- service

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

#### Docker swarm cluster (Play With Doker)

- ##### สร้างเครื่อง 3 เครื่อง (node1, node2, node3)

- ##### ทำการสร้าง swarm node1 เป็น manager

      เริ่มต้น mode docker swarm
      docker swarm init --advertise-addr=192.168.0.28
      
      แสดงรายการข้อมูลของ node ซึ่ง node manager เท่านั้นที่ใช้คำสั่งนี้ได้
      docker node ls
 
- ##### ทำการสร้าง swarm node2 เป็น worker node

      docker swarm join --token SWMTKN-1-5r3sdl8qx8qjzcwy54rywa62m3lt83sbyvu6mm2jej2xbpccpl-6bqbothq4pf39xsg8xl1ozjfo 192.168.0.28:2377

- ##### ทำการสร้าง swarm node3 เป็น worker node

      docker swarm join --token SWMTKN-1-5r3sdl8qx8qjzcwy54rywa62m3lt83sbyvu6mm2jej2xbpccpl-6bqbothq4pf39xsg8xl1ozjfo 192.168.0.28:2377
