
- secret เป็นส่วนหนึ่งของ dokcer swarm สามารถใช้ได้ใน swarm 


#### คำสั่งสร้าง secret อ่านค่าจาก command 

    
    printf zaq12wsx | docker secret create my_secret -
    
    หากไม่มี printf command ให่ใช้ echo แทน
    echo zaq12wsx | docker secret create my_secret -
