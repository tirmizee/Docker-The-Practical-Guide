
### docker swarm commands

- node คือ instance ของ Docker engine ที่เข้าร่วมใน Docker swarm. สามารถเรียกใช้ node อย่างน้อยหนึ่งโหนดบนคอมพิวเตอร์จริงเครื่องเดียวหรือเซิร์ฟเวอร์คลาวด์ แต่การใช้งาน production โดยทั่วไปจะรวมโหนด Docker ที่กระจายอยู่ในเครื่องทางกายภาพและคลาวด์หลายเครื่อง
- service

##### เริ่มต้น docker swarm

      docker swarm init

##### แสดงการทำงาน node ของ docker swarm

      docker node ls

##### แสดงการทำงาน service/container ของ docker swarm

      docker service ls

##### แสดงการทำงาน service ที่ระบุ

      docker service ps <ID|NAME>

##### แก้ไข service ที่ระบุ โดยการเพิ่มจำนวน service

      docker service update <ID> --replicas 3 
