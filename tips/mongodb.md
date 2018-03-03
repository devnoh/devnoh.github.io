# MONGODB

## Inatllation

$ brew install mongo

To have launchd start mongodb now and restart at login:
  brew services start mongodb
Or, if you don't want/need a background service you can just run:
  mongod --config /usr/local/etc/mongod.conf

## Connection

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

> db.getCollection('icc_inventory').find({"vehicleData.VehicleInfo.ExteriorColor":{$eq:''}}).count()
> db.getCollection('icc_inventory').find({"vehicleData.VehicleInfo.ChromeStyleID":{$gt:-1}}).count()
> db.getCollection('icc_inventory').find({"vehicleData.VehicleInfo.ExteriorColor":{ "$regex":"pw7/tlx9/pw7", "$options":"-i" }})

> db.getCollection('vehicle_description').distinct("vin").length;
> db.getCollection('vehicle_description').find({"rawData.exteriorColor":{ $size: 0 }})

