#### Secret

- secret คือความลับของข้อมูล เช่น password private key SSL certificate หรือข้อมูลอื่นๆ ที่ไม่ควรส่งผ่านเครือข่ายหรือจัดเก็บโดยไม่ได้เข้ารหัส ใน Dockerfile หรือในซอร์สโค้ดของแอปพลิเคชันของคุณ
- สามารถใช้ Docker secret เพื่อจัดการข้อมูลนี้จากส่วนกลางและส่งไปยังคอนเทนเนอร์ที่ต้องการเข้าถึงได้อย่างปลอดภัย
- Docker secret ใช้ได้เฉพาะกับ Docker swarm เท่านั้น

#### docker secret commands

- docker secret create
- docker secret inspect
- docker secret ls
- docker secret rm
- --secret flag สำหรับ docker service create
- --secret-add และ --secret-rm flags สำหรับ docker service update

#### docker secret ls

- ##### แสดงรายการ secret ทั้งหมด

        docker secret ls
    
#### docker secret create

- ##### คำสั่งสร้าง secret อ่านค่าจาก command 

    
        printf zaq12wsx | docker secret create my_secret -
    
        หากไม่มี printf command ให้ใช้ echo แทน
        echo zaq12wsx | docker secret create my_secret -
    
- ##### คำสั่งสร้าง secret อ่านข้อมูลจาก file secret.txt

        cat secret.txt
        zaq12wsx
        
        docker secret create sql_secret secret.txt
