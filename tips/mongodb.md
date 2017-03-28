# MONGODB

$ mongo
```
> use admin
> db.createUser({user:"admin",pwd:"admin",roles:[{role:"userAdminAnyDatabase",db:"admin"}]})
```

$ mongod --auth --port 27017 --dbpath /data/db

$ mongo --port 27017 -u "admin" -p "admin" --authenticationDatabase "admin"
