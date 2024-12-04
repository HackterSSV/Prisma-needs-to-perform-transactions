# when you have problem
Prisma needs to perform transactions, which requires your MongoDB server to be run as a replica set. 

# we can use this step
1. install mongodb server
   
    https://www.mongodb.com/try/download/community

2. open terminal and run
   
    mongod --replSet "rs0"
   
3. restart mongodb service
4. 
5. install mongodb shell and run
   
      1. install mongodb shell
            https://www.mongodb.com/try/download/shell
      
      2.open mongodb shell and conect to your host
   
      3.run command: rs.initiate()
   
6. connect mongo compass
## you can connect mongo compass



##Use mongo in docker 
1. runcomand in project:
   1.openssl rand -base64 756 >mongodb-keyfile // gennerate replica key
   2.chmod 400 mongodb-keyfile //ກຳນົດສຶດໃຫ້ໄຟ
3. set update docker compose
   version: '3.9'
   services:
     mongodb:
       image: mongo:latest
       container_name: mongo
       environment:
         - MONGO_INITDB_ROOT_USERNAME=rmsAdmin
         - MONGO_INITDB_ROOT_PASSWORD=rms@admin2024
       volumes:
         - ./mongodb-keyfile:/etc/mongodb-keyfile:ro
       command: mongod --replSet rs0 --auth --keyFile /etc/mongodb-keyfile
       ports:
         - "27017:27017"
4. run docker compose
   docker compose up -d
5. run comand in terminal
   docker exec -it <containername> mongosh -u <username> -p <passaword> --authenticationDatabase admin // username and password ໃຊ້ທີ່ຂຽນຢູ່ docker compose
6. run this :
   rs.initiate({
  _id: "rs0",
  members: [
    { _id: 0, host: "localhost:27017" }
  ]
});

if output is: rs0 [direct: other] test> is succes
