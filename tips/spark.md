# SPARK

### Tools
http://spark-notebook.io

### Examples
```scala

scala> val licLines = sc.textFile("/usr/local/spark/LICENSE")
licLines: org.apache.spark.rdd.RDD[String] = /usr/local/spark/LICENSE MapPartitionsRDD[1] at textFile at <console>:24

scala> val lineCnt = licLines.count
lineCnt: Long = 299

scala> def isBSD(line: String) = { line.contains("BSD") }
isBSD: (line: String)Boolean

scala> val isBSD = (line: String) => line.contains("BSD")
isBSD: String => Boolean = <function1>

scala> val bsdLines1 = licLines.filter(isBSD)
bsdLines1: org.apache.spark.rdd.RDD[String] = MapPartitionsRDD[2] at filter at <console>:28

scala> bsdLines1.count
res0: Long = 33

scala> bsdLines1.foreach(line => println(line))
BSD-style licenses

scala> val numbers = sc.parallelize(10 to 50 by 10)
numbers: org.apache.spark.rdd.RDD[Int] = ParallelCollectionRDD[3] at parallelize at <console>:24

scala> numbers.foreach(x => println(x))
10
20
30
40
50

scala> val numbersSquared = numbers.map(num => num * num)
numbersSquared: org.apache.spark.rdd.RDD[Int] = MapPartitionsRDD[4] at map at <console>:26

scala> numbersSquared.foreach(x => println(x))
100
400
900
1600
2500

```
