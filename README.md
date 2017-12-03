# docker-command

docker pull apache:2.0  download docker  <br>

docker run --name testapache -v ~/www:/usr/share/www/html:ro -p 80:80 -d apache:2.0 <br>
  --name testapache กำหนดชื่อ <br>
  -v ~/web:/usr/share/nginx/html:ro     map folder ระหว่าง docker กับ pc   ( :ro option ในการอ่าน read only) <br>
  -p 80:80                              map port ระหว่าง docker กับ pc <br>
  -d apache:2.0                         กำหนด container ที่ต้องการ run <br>
  
docker ps ดู Container ทั้งหมดเฉพาะที่กำลังทำงานอยู่ เอาไว้ใช้ดู CONTAINER_ID ได้ด้วยครับ <br>
docker ps -a ดู Container ทั้งหมดรวมถึงตัวที่ stop pause หรือทำงานเสร็จแล้ว <br>
docker stop CONTAINER_ID หยุดการทำงาน Container <br>
docker start CONTAINER_ID เริ่มการทำงาน Container <br>
docker rm CONTAINER_ID ลบ Container  (ต้อง stop หรือ kill ก่อน) <br>
docker inspect CONTAINER_ID ดูข้อมูล Container อย่างละเอียด <br>
docker logs CONTAINER_ID ดูข้อมูลการทำงานของ Container <br>
docker exec -it CONTAINER_ID bash เข้าไปที่เครื่อง Container (เหมือน SSH เข้าไป) <br>

 <br>
docker stop testapache  <br>
docker rm testapache  ||  docker rmi container id <br>


#docker compose <br>
Go to directory  <br>

docker-compose up -d   # run compose <br>
docker-compose ps      # check service <br>
docker exec -it lemp_nginx sh   #into docker service <br>
docker-compose stop     # stop all in docker file <br>
docker-compose stop php  #stop only once <br>
docker-compose start  # start all  <br>
docker-compose start php  # start onec service <br>
 <br>
Log <br>
docker-compose log       # view log <br>
docker-compose log php   # view log php <br>
 <br>
# stop and delete all <br>
docker-compose down <br>
