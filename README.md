# when you have problem
Prisma needs to perform transactions, which requires your MongoDB server to be run as a replica set. 

# we can use this step
1. install mongodb server
   
    https://www.mongodb.com/try/download/community
3. install mongodb shell
   
   https://www.mongodb.com/try/download/shell
4. open terminal and run
   
    mongod --replSet "rs0"
5. open mongo shell and run
   
   1.rs.initiate()
   2.rs.initiate( {
   _id : "rs0",
   members: [
                  { _id: 0, host: "yourId:27017" }
            ]
  })

## you can connect mongo compass
   
   
   
