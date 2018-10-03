# Java 11

## jlink (The Java Linker)

$ jlink --module-path $JDKMODS --addmod java.base --output myimage
$ jlink --module-path $JDKMODS:$MYMODS --addmod com.devnoh --output myimage

$ myimage/bin/java --list-modules

## Local Variable Type Interface

var list = new ArrayList<String>();
var stream = list.stream();

## 73 New APIs in JDK 10

* List, Set, Map.copyOf(Collection)
* Collectors
  - toUnmodifiableList
  - toUnmodifiableMap
  - toUnmodifiableSet
* Optional.orElseThrow()
* XMLInputFactory.newFactory() -> de-deprecated
* com.su.security.auth package -> 6 classes removed
* java.lang.SecurityManager -> 1 filed & 7 methods removed
* JVM now more Docker container aware

## Dynamic Class-File Constants

## Epsilon GC

* A non-collecting garbage collector

## HTTP Client (Standard)

* java.net.http module and package
  - HttpClient
  - HttpRequest
  - HttpResponse
  - WebSocket

## Extend Local-Variable Syntax

list.stream()
  .map((@NotNull) var s) -> s.toLowerCase())
  .collect(Collections.toList());

## Unicode 10 Support

* 8518 new characters
* Colbert emoji

## Launch Single File Source Code

$ java Factorial.java 4

Single File Source Code Shebanng
```
$ $JAVA_HOME/bin/java --source 11
$ ./Factorial 4
```

## Others

* TLS 1.3
* Nashorn JavaScript Engine deprecated
* ...

## New APIs

* new I/O methods
  - nullInputStream(), nullOutputStream(), nullReader(), nullWriter()
* Optional
  - isEmpty()
* Character
  - toString(int)
* String
  - isBlank(), Stream lines(), repeat(int), strip(), stripLeading(), stripTrailing()
* Predicate not(Predicate)
  - lines.stream().filter(Predicate.not(String::isBlank))