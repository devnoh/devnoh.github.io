# SCALA

### Install

$ brew install scala

### Examples
```scala

scala> List(1, 2, 3, 4, 5).sum
res0: Int = 15

scala> List(1, 2, 3, 4, 5).foldLeft(0)((r, x) => r + x)
res3: Int = 15

scala> List(1, 2, 3, 4, 5).foldLeft(0)(_ + _)
res4: Int = 15

scala> List(1, 2, 3, 4, 5).map(m => m *2).foldLeft(0)(_ + _)
res5: Int = 30

scala> List(1, 2, 3, 4, 5).map(m => m * 2).foldLeft(0)((r, x) => r + x)
res7: Int = 30

scala> List(1, 2, 3, 4, 5).map(_ * 2).foldLeft(0)((r, x) => r + x)
res8: Int = 30

scala> (1 to 5).sum
res12: Int = 15

scala> (1 to 5).map(_ * 2).sum
res13: Int = 30

scala> (1 to 5).map(_ * 2).filter(_ < 7).sum
res15: Int = 12

```
