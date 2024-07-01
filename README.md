# when you have problem
Prisma needs to perform transactions, which requires your MongoDB server to be run as a replica set. 

# we can use this step
1. install mongodb server
   
    https://www.mongodb.com/try/download/community

4. open terminal and run
   
    mongod --replSet "rs0"
   
6. restart mongodb service
7. install mongodb shell and run
   
   1. install mongodb shell
         https://www.mongodb.com/try/download/shell
      
   2.open mongodb shell and conect to your host
   
   3.run command: rs.initiate()
8. connect mongo compass
## you can connect mongo compass
   
   
   
