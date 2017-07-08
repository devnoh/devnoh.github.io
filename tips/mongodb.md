# MONGODB

$ mongo
```
> use admin
> db.createUser({user:"admin",pwd:"admin",roles:[{role:"userAdminAnyDatabase",db:"admin"}]})
```

$ mongod --auth --port 27017 --dbpath /data/db

$ mongo --port 27017 -u "admin" -p "admin" --authenticationDatabase "admin"


## Query

> db.getCollection('inventory').distinct("modelName");
> db.getCollection('inventory').aggregate({$group: {_id : "$modelName", number:  { $sum : 1} }} )
> db.getCollection('inventory').aggregate({$group: {_id : {book : '$book', address:'$addr'}, number:  { $sum : 1} }} )

> db.getCollection('inventory').aggregate({$group: {_id : {extColor : '$vehicleData.VehicleInfo.ExteriorColor', genericExtColor:'$vehicleData.VehicleInfo.GenericExteriorColor'}, number:  { $sum : 1} }} )

> db.getCollection('icc_inventory').find({"vehicleData.VehicleInfo.ChromeStyleID":{$gt:-1}}).count()
