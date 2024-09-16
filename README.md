# Java-Application-Performance-Tuning-and-Memory-Management

This repository contains, coding tips and tools for Java Appliaction Performance tuning and Memory management.

When we write a java code, its is complied by JDK into .class file also called as byte code. When this byte code is run by JVM, it interprets the code line by line. There is one component in JVM called as JIT Compiler or Just in Time compiler. It converts the most frequent part of code into machine code, thus enabling faster application performance.
JVM JIT again has two types of compilers C1 and C2 compilers. C2 compiler is called on a method if it has been called very frequently in the application.
So, basically code cache is the memory space in java program where C2 compiled code will be stores, and thus we should ensure we have enough sized code cache for better performance.

## Compiler Flags

1. -XX:+PrintCompilation -> Tells about how the code is compiled, which method is kept in code cache and tells alot above the code peroformance.
2. -XX:+PrintCodeCache -> To print the size of code cache. It can be expanded upto certain limits.
3. -XX:ReservedCodeCacheSize -> To set custom code cache size it can be 28, 28k, 28m etc values.
