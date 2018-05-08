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

## Swift
Swift uses modules instead of class prefixes, so the module's name is the namespace for all its classes. Similarly to java, it uses *import* to use them

To import a module: `import FrameWork`

# Types
## Java
List of primitive types:
1. byte
2. short
3. int
4. long
5. float
6. double.
7. boolean
8. char
Reference types:
1. Objects
2. Enums

Both rerence and value types in java, as seen above. However, new value types cannot be created, you can only use the eight preexisting ones.

## Swift
Swift has two types: named types and compound types. The important one of these is named types, as these include classes, structures, enumerations, and protocols. Swift also includes many common types such as types for numbers and strings. Swift does allow for both reference and value types, for example a class would be a reference type and an enum is a value type. A programmer can also create or extend named types in Swift. 

# Classes 
## Java
The following code defines a clas and creates a constructor for it. The constructor uses the same name as the class, and is called to create a new instance by using the keyword *new* followed by the contructor e.g. `new House()`. There are no true destructors in java, as that is handled by the garbage collector. There is a method called finalize, however it is only called by the garbage collector.
```
//defines a new class, House
public class House {
    //below are constuctors
      public House() {
      }
      
      public House(String name) {
      
      }
    } 
```

## Swift
The following code defines a class called Student. In order to create a new instance you simply call the class name e.g. `student()`. To initialize you use the keyword *init*, and Swift does have a destructor called *deinit*. This is run automatically by ARC, however in some cases such as writing to a file you must close the file in order for the class to be deallocated.
```
//defines a new class, student
class student {
   var name: String
   var grade: Int 
}
```

# Instance reference name in data type (class)
## Java 
Java uses the keyword *this*
```
public class Point {
    public int x = 0;
    public int y = 0;
        
    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```

## Swift
Swift uses the keyword *self*
```
class Counter {
    var count = 0
    func increment() {
        count += 1
    }
    func increment(by amount: Int) {
        self.count += 1
    }
    func reset() {
        count = 0
    }
}
```

# Properties
## Java
In Java you must write your own getter and setters, and there is no built in backing field/variable. Jave does not have computed properties.

## Swift
Swift classes have built in setter and getter methods that the programmer can define. Swift also has backing stores and allows computed properties.

# Interfaces / Protocols
## Java
