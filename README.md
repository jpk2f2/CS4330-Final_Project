# CS4330-Final_Project

# Language Purpose/Genesis
## Java
Java was initially developed for use in interactive television, however this use never materialised and it was eventually publicly released by Sun Microsystems in 1995. It was created as a cross-platform language where you could write the code once and then run it many different platforms. It was meant to follow five principles:
1. simple, object-oriented, and familiar: easy to pick up; syntax based off of C++
2. robust and secure: highly reliable, simple memory management avoids issues seen in C and C++
3. architecture-neutral and portable: Cross-platform, Java virtual machine
4. high performance: exellent end user performance
5. interpreted, threaded, and dynamic: multithreading capability and dynamic linking from libraries

Java was heavily influenced by C and C++ in that it based much of its syntax off of them, and that some of its design choices were made to avoid problems found in those languages

## Swift
Swift was developed and released by Apple as an object orientated programming language for the various Apple operating systems. The language was created as an alternative to Objective-C, however it still supports code written in Objective-C. Swift was created to solve problems existing in the Objective-C framework, as well as to add additional features. Some of these key changes are the addition of memory management, improved debugging, and simpler syntax. So in this way, Swift is very much a replacement for Objective-C in that it is heavily based off of it, however with the addition of many changes Apple saw necessary. 

# Unique features of the language
## Java
* architecture-neutral and portable: Java has the JVM, or java virtual machine. This allows its code to be run on any platform that has the JVM
* automatic garbage collector: this runs in the background and works automatically, allowing memory to be available as needed.

## Swift 
* access control: Swift has five levels of access control, what makes them unique is that they ignore inheritance. These levels are:
1. open: can be subclassed outside the module
2. public: any module
3. internal: containing module
4. fileprivate: within file
5. private: immediate scope
* optionals: Allows references to point to either a value or be null. This exists in other languages, but not generally oop languages
* runtime: Swift uses the same runtime as Objective-C
* memory management: ARC, or Automatic Reference Counting

# Name spaces
## Java
Java uses packages which are a named collection of classes, these define a namespace for those classes. A fully qualified name would include the entire name space, that is, appending the class name to the package name. They are utilized by the use of the keyword *import* as seen in the examples below

To import a specific class: `import java.io.File;`

To import an entire package: `import java.io.*;`

