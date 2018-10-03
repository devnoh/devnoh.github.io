# Java 11

## jlink (The Java Linker)

$ jlink --module-path $JDKMODS --addmod java.base --output myimage
$ jlink --module-path $JDKMODS:$MYMODS --addmod com.devnoh --output myimage

$ myimage/bin/java --list-modules
