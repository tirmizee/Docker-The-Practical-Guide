
### docker swarm commands

- node คือ instance ของ Docker engine ที่เข้าร่วมใน Docker swarm. สามารถเรียกใช้ node อย่างน้อยหนึ่งโหนดบนคอมพิวเตอร์จริงเครื่องเดียวหรือเซิร์ฟเวอร์คลาวด์
- service

##### เริ่มต้น docker swarm

      docker swarm init

##### แสดง node ของ docker swarm

      docker node ls

##### xxx

      docker service ls

##### xxxx

      docker service ps <ID|NAME>

##### xxxx 

      docker service update <ID> --replicas 3 
