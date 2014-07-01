# Homework 2.1

Download and uncompress the folder.

`cd hw2_1`

Restore csv data:

`mongoimport --type csv --headerline weather_data.csv -d weather -c data`


Verify you've imported correctly the data, in the mongo shell.
```
> use weather
> db.data.find().count()
> 2963
```

## Answer

In the mongo shell
```
> db.data.find({'Wind Direction' : {$gt: 180,$lt:360}},{'State':1, Temperature: 1}).sort({Temperature: 1}).limit(1)
{ "_id" : ObjectId("53b1e8357dc478bc6ab48936"), "State" : "New Mexico", "Temperature" : 0 }
```

And the answer is ```New Mexico```
