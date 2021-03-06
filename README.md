# Java API for the Logitech LCD G19 gaming keyboard

**David Powell <djpowell@djpowell.net> 2010-04-11**

**<http://github.com/djpowell/lcdjni>**


This software is distributed under the MIT licence.

----------------------------------------


**New download location**: http://djpowell.net/files/lcdjni-1.0.0-rc5.zip


Description
-----------

An API for writing applets for the Logitech G19 LCD gaming keyboard.

This package provides a JNI DLL which is used by a Java API to allow
applets to draw on the screen, read the softkeys, and subscribe to
events.  This API is a wrapper around the lglcd.h C API, so
familiarity with that API may help in undestanding it.

The API should also support other compatible devices, including black
& white devices such as the Logitech G15 Keyboard, but this hasn't
currently been tested.

----------------------------------------

Deployment
----------

If you are using a 32-bit JVM, you must use the 32-bit DLL.

If you are using a 64-bit JVM, you must use the 64-bit DLL.

For most client applications, the 32-bit JVM is probably the most
suitable, as the 64-bit JVM doesn't currently provide a client VM in
addition to the server VM.

The correct DLL should be included on the library path.  The easiest
way to do this is by copying it to the working directory of your
application's executable jar or script.  Alternatively you can use the
startup flag:

```
-Djava.libary.path=<directory-containing-the-dll>
```

----------------------------------------

Running the examples
--------------------

Three examples are provided:

```
  net.djpowell.lcdjni.examples.HelloWorld
  net.djpowell.lcdjni.examples.HelloWorldMono
  net.djpowell.lcdjni.examples.HelloWorldDual
  net.djpowell.lcdjni.examples.EventTest
```  

To run the examples using a 32-bit JVM:

```
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x86 net.djpowell.lcdjni.examples.HelloWorld
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x86 net.djpowell.lcdjni.examples.HelloWorldMono
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x86 net.djpowell.lcdjni.examples.HelloWorldDual
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x86 net.djpowell.lcdjni.examples.EventTest
```

To run the examples using a 64-bit JVM:

```
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x64 net.djpowell.lcdjni.examples.HelloWorld
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x64 net.djpowell.lcdjni.examples.HelloWorldMono
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x64 net.djpowell.lcdjni.examples.HelloWorldDual
  java -cp lcdjni.jar;lcdjni-examples.jar -Djava.library.path=x64 net.djpowell.lcdjni.examples.EventTest
```

----------------------------------------

Notes
-----

LCD Manager uses the executable name of your process to support auto
startable applications.  Therefore, it only makes sense to pass 'true'
to the isAutoStartable parameter of the LcdConnection constructor if
you have some way to start your java application using a command-line
that doesn't require parameters.  For example, by launching Java using
the JNI invocation API.

