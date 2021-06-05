
##### สร้าง private registry

    สร้าง service registry สำหรับ docker swarm
    docker service create --name registry --publish published=5000,target=5000 registry:2

    สร้าง contrainer registry สำหรับ docker 
    docker run -d -p 5000:5000 --restart=always --name registry -v //d/registry/config.yml:/etc/docker/registry/config.yml registry:2
