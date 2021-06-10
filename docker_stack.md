### Docker stack

- ใน Docker V1.13 ได้เพิ่มชั้นของนามธรรมไปยัง swarm เรียกว่า stack
- stack สามารถใช้ compose-file สหรับกำหนด Service, Network และ Volume
- ใช้ docker stack deploy แทน docker service create
- compose ละเว้นคำสั่ง deploy ส่วน stack ละเว้นคำสั่ง build
- docker-compose cli ไม่จำเป็นสำหรับ docker swarm

### Stack ignore command

- build
- depends_on

##### deploy stack ใหม่หรืออัปเดต stack ที่มีอยู่

    docker stack deploy -c <compose.yml> <stack_name>

##### compose file

### Reference

- https://docs.docker.com/engine/reference/commandline/stack_deploy/
