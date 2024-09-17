# Java-Application-Performance-Tuning-and-Memory-Management

This repository contains, coding tips and tools for Java Appliaction Performance tuning and Memory management.

When we write a java code, its is complied by JDK into .class file also called as byte code. When this byte code is run by JVM, it interprets the code line by line. There is one component in JVM called as JIT Compiler or Just in Time compiler. It converts the most frequent part of code into machine code, thus enabling faster application performance.
JVM JIT again has two types of compilers C1(Client) and C2(Client & Server) compilers. C2 compiler is called on a method if it has been called very frequently in the application.
So, basically code cache is the memory space in java program where C2 compiled code will be stores, and thus we should ensure we have enough sized code cache for better performance.

## 32 bit JVM vs 64 bit JVM
There is difference between the JVM version 32 bit and 64 bit. If the machine is 32 bit then there is obvious choice but if you have 64 bit machine then you have to decide which version of JVM you want to use for your application.

1. 32 BIT JVM - Better performance for small heap sized applications. Max heap size can be only upto 4GB. only C1 compilers are present. Should be used for client, small lived applications. Quicker startup time. `-client` flag should be used while running program on 64 bit JVM if we want to use 32 bit JVM
2. 64 BIT JVM - Better performance for large heap sized applications. Max heap size is OS dependent. Both C1 & C2 compilers are present. Should be used for server applications.

## Compiler Flags

1. -XX:+PrintCompilation -> Tells about how the code is compiled, which method is kept in code cache and tells alot above the code peroformance.
2. -XX:+PrintCodeCache -> To print the size of code cache. It can be expanded upto certain limits.
3. -XX:ReservedCodeCacheSize -> To set custom code cache size it can be 28, 28k, 28m etc values.
4. -XX:-TiredCompilation -> To turn of compilation and only to interpretation of code.
5. -XX:+PrintFlagsFinal -> To print all the available JVM flags
6. -XX:CICompilerCount=X -> Number of threads present for code compilation
7. -XX:CompileThreshold=X -> The minimum threshold amount the method should be run in order to be compile cached.
