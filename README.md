# CS4330-Final_Project
# Comparing Java and Swift
#### By: Jason Kayser

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
Java allows the creation and use of interfaces, but not protocols. These allow for polymorphism, as they can contain method signatures and fields. This is similar to a class, they main difference being that an interface cannot implement the methods. A class can implement as many interfaces as you want, and are used by calling the keyword *implements*.
```
public class foo implements bar,bar2{} //bar and bar2 are interfaces
```

## Swift
Swift does not have interfaces, but rather protocols, which do share some features with interfaces. Protocols allow the specification of properties to implemented, and similarily many can be used. Protocols are more versatile than interfaces, as they can also be used as types. Protocols are implemented by using a colon.
```
protocol stname {
   var name: String { get }
}
protocol stage {
   var age: Int { get }
}
struct Person: stname, stage {
   var name: String
   var age: Int
}
```

# Inheritance / extension
## Java
Java allows the creation of parent and child classes, known as super and sub classes. Java does not support multiple inheritance, so each sub class can only have a single super class. In order to inherit the properties of the super class, the keyword *extends* is used. The *super* keyword can also be used to access the super class' constructor or to differentiate the members of each. 
```
class Super{
    public void foo(){
    }
}
class Sub extends Super {
    public void foo(){
    }
    public void bar(){
    Sub sub = new Sub();
    //call sub class foo()
    sub.foo();
    //call super class foo()
    super.foo();
    }    
}
```
## Swift
Similarly to Java, Swift does not allow for multiple Inheritance. Swift has sub and super classes, meaning the sub classes can inherit properties, methods, and functions from a super class. In order to declare a subclass a colon is used, similar to the protocols. Unlike Java, if you wish to use the same name for properties or methods in a sub class, the keyword *override* must be used. The keyword *super* can also be used to access methods or properties from the super class. 
```
class Super{
    init(){}
    func foo(){}
}
//uses : to define subclass
class Sub : Super {
    init(){
    //uses super to call method from super class
        super.init()
    }
    //overrides the super's function with a new one
    override func foo(){}
}
```
# Reflection
## Java
Reflection can be used by including the package `java.lang.reflect`. This allows you to obtain the names of an object's members, as well as examine and modify its behavior at runtime.
```
//get method names into array
Method[] methods = foo.getMethods();
//print method names
for (Method method:methods){
    System.out.println(method.getName());
}
```
## Swift
Reflection is supported in Swift, allowing limited read-only access to the properties of an instance, i.e. you cannot access computed properties or functions. In order to utilize reflection, you make use of a struct called *Mirror*.
```
let foo = bar()
//creates Mirror of foo
let fooMirror = Mirror(reflecting: foo)
//print out all values(metadata)
for case let(label?,value) in fooMirror.children{
    print(label,value)
}
```
# Memory Management
## Java
In general, Java allocates memory for you, and the garbage collector automatically deallocates them when they are no longer needed. The garbage collector utilizes a heap, placing new items on it and removing old ones. You can still directly access memory in limited ways, such as mapping memory into a ByteBuffer or through a framework like jmalloc which uses memory outside the heap. Java does not do auatomatic reference counting. 
## Swift
Swift uses ARC, or Automatic Reference Counting for its memory management. This system tracks the number of references to an object, and deallocates it once that number hits zero. This prevents it from accidentally deallocatinig memeory that is in use. Swift also allows both *weak* and *strong* references. A strong reference will keep the ARC from destroying the linked object, while a weak reference will not. If an object is removed, any weak references will be set to nil. 

# Comparisons of references and values
## Java
There are two ways to compare objects. The first of these is by value, the second is by reference. To compare, for example, two strings, you can use the object method *equals()*. This will compare their values, and if both strings are the same it will return true. On the other hand, you can use == to compare them by reference. This will be true only if the two objects are literally the same, i.e. the same object, not just the same value. 
```
String string1 = new String("foo")
String string2 = new String("foo")
String string3 = new String("bar")

string1.equals(string3); //false
string1.equals(string2); //true
string1 == string2; //false
string1 == string3; //false
string2 = string1;
string1 == string2; //true
```

## Swift
In Swift, the == is used to compare values even for objects, while the === is used for comparing reference. 
```
var string1 = "foo"
var string2 = "foo"
var string3 = "bar"
string1 == string2 //true
string1 == string3 //false
string1 === string2 //false
string1 === string3 //false
string1 = string2
string1 === string2 //true
```

# Null/nil references
## Java
Java uses null, and it will throw a NullPointerException if you attempt to use a null reference. Null should be avoided. 
## Swift
Swift uses nil, and allows for the use of nil values in optionals. This allows a property to be set to nil without throwing an error.
# Errors and exception handling
## Java
Error/exception handling in Java is based around the try-catch design. An error or exception is thrown, and then it is caught in the try-catch. 
```
try{
    ... //some code that throws an error
    ...
} catch(Exception e){
    ... //some error handling logic
}
```
## Swift
Swift handles errors through the use of the *Error* protocol. This works well with an enumeration:
```
enum DoctorOfficeError: Error {
    case noAppointment
    case closed
    case tooPoor(cost: Int)
    case doctorSick
}
```
and the errors can then be thrown using *throw*:`throw DoctorOfficeError.closed`
Within a method you can then use guards to throw these errors, as well as do-catch, or try statements in code calling that method in order to handle the thrown errors.

# Lamba expressions, closures, or functions as types
## Java
Java allows for lambda expressions, but it does not have closures or functions as types. Lambda expressions allow for functional programming, and the replacement of anonymous classes. It uses the syntax of *parameter -> expression body* e.g.:
```
Operation multiplication = (int a, int b) -> { return a * b; };
```
## Swift
Swift does not have lambdas, instead they have closures which are very similar. Closures use the syntax of:
```
{ (parameters) -> return type in
    statements
}
```
Swift also allows for the use of functions as types, as it considers functions as a compound type. Rather than a name, compound types have a signature, i.e. its parameters and return type.  
# Implementation of listeners and even handlers
## Java
Java ties listeners to events, allowing for specific actions to take place upon triggering it. Lambdas are frequently used for these tasks: `button.addActionListener(a -> buttonClick() );` this calls the method buttonClick whenever the button is clicked. 
## Swift
Swift does not have the same listener and event handling capabilities that java does, instead it is handled a bit differently. One alternative is Key-Value Observing, or KVO. This allows an object ot be notified of changes to specific properties in another class. 
```
class Oberserved: NSObject {
    @obj dynamic var x = 0;
    func updateX(){
        x += 1
    }
}
class Observer: NSObject {
    @obj var observerdX: Observed
    var observation: NSKyValueObservation?
    
    observation = observe(\.observedX.x) {object, change in //some action here 
                                         }
    
 ```
# Singleton
## Java
To create a singleton in Java you must make a class with a private constructor and give it a static method with a return type of the singleton class. This methed utilizes lazy initialization. Singletons in Java are not necessarily thread safe, as multiple threads can access it at the same time, leading to the creation of it twice. 
## Swift
Swift singletons are made utilising class constants and a private init. This supports lazt initialization and is thread safe. 
```
class Singleton  {
   static let sharedInstance = Singleton()
   private init() {}
}
```
# Procedural programming
## Java
Java is fundamentally object orientated, however you could certainly imitate the procedural programming methodology. 
## Swift
Swift is a multi-paradigm language, which is designed around programming in both procedural and object oriented.
# Functional programming
## Java
Java can perform functional programming, for example this higher order function:
```
public static Integer calculate(Function<Integer, Integer> function, Integer value) {
    return function.apply(value);
}
```
Java has some features that allow for this, such as the java.util.Function<T,R> Interface which was used above and lambda expressions.
## Swift
Swift also allows for functional programming, and it even defaults to making properties immutable. 
```
let array = [
    Test(name: "test1",types: [...], x:4),
    Test(name: "test2",types: [...], x:9),
    Test(name: "test3",types: [...], x:7)
    ]
    
array[1] = Test(name: "foo",types: [...], x:1) //throws error b/c array is immutable
```
# Multithreading 
## Java
One of java's core principles revolves around threads, for example all of java's main libraries are designed to be thread safe. Java threads are easily created through implementing the *runnable* interface or by setting *Thread* as the parent. 
## Swift
Swift also allows for multithreading, very similarily to Objective-C. It utilises dispatch_async:
```
let priority = DISPATCH_QUEUE_PRIORITY_DEFAULT
dispatch_async(dispatch_get_global_queue(priority, 0)) {
	// some code1
	dispatch_async(dispatch_get_main_queue()) {
		// some code2
	}
}
```
