# docker-command

docker pull apache:2.0  download docker

docker run --name testapache -v ~/www:/usr/share/www/html:ro -p 80:80 -d apache:2.0
  --name testapache กำหนดชื่อ
  -v ~/web:/usr/share/nginx/html:ro     map folder ระหว่าง docker กับ pc   ( :ro option ในการอ่าน read only)
  -p 80:80                              map port ระหว่าง docker กับ pc
  -d apache:2.0                         กำหนด container ที่ต้องการ run
  
docker ps ดู Container ทั้งหมดเฉพาะที่กำลังทำงานอยู่ เอาไว้ใช้ดู CONTAINER_ID ได้ด้วยครับ
docker ps -a ดู Container ทั้งหมดรวมถึงตัวที่ stop pause หรือทำงานเสร็จแล้ว
docker stop CONTAINER_ID หยุดการทำงาน Container
docker start CONTAINER_ID เริ่มการทำงาน Container
docker rm CONTAINER_ID ลบ Container  (ต้อง stop หรือ kill ก่อน)
docker inspect CONTAINER_ID ดูข้อมูล Container อย่างละเอียด
docker logs CONTAINER_ID ดูข้อมูลการทำงานของ Container
docker exec -it CONTAINER_ID bash เข้าไปที่เครื่อง Container (เหมือน SSH เข้าไป)


docker stop testapache 
docker rm testapache  ||  docker rmi container id


#docker compose
Go to directory 

docker-compose up -d   # run compose
docker-compose ps      # check service
docker exec -it lemp_nginx sh   #into docker service
docker-compose stop     # stop all in docker file
docker-compose stop php  #stop only once
docker-compose start  # start all 
docker-compose start php  # start onec service

Log
docker-compose log       # view log
docker-compose log php   # view log php

# stop and delete all
docker-compose down
