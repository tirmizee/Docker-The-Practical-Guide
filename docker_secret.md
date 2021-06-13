#### Secret

- secret คือความลับของข้อมูล เช่น password private key SSL certificate หรือข้อมูลอื่นๆ ที่ไม่ควรส่งผ่านเครือข่ายหรือจัดเก็บโดยไม่ได้เข้ารหัส ใน Dockerfile หรือในซอร์สโค้ดของแอปพลิเคชันของคุณ
- secret เป็นส่วนหนึ่งของ dokcer swarm สามารถใช้ได้ใน swarm 


##### แสดงรายการ secret ทั้งหมด

    docker secret ls

##### คำสั่งสร้าง secret อ่านค่าจาก command 

    
    printf zaq12wsx | docker secret create my_secret -
    
    หากไม่มี printf command ให่ใช้ echo แทน
    echo zaq12wsx | docker secret create my_secret -
    
##### คำสั่งสร้าง secret อ่านข้อมูลจาก file
