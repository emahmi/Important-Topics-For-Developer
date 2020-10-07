## Question-1 

### Class
A class is like a blueprint of a specific object. In object-oriented programming, a class defines some properties, fields, events, methods, etc. A class defines the kinds of data and the functionality their objects will have. A class enables you to create your custom types by grouping variables of other types, methods, and events.

### Enum
An enum lets you declare a series of identifiers for use in your code. The compiler replaces them with numbers for you. It's often useful for making your code more readable and maintainable, because you can use descriptive names without the performance penalty of string comparisons. 

### Struct
A struct contains zero or more pieces of data (variables or objects), grouped together so they can be stored, processed, or passed as a single unit. A struct can be a lot more complex though. It's actually exactly the same as aclass, except that members are public by default instead of private. Like a class, a struct can have member functions and template parameters and so on.

### Interface
An interface can be defined using the interface keyword. An interface can contain declarations of methods, properties, indexers, and events. However, it cannot contain fields, auto-implemented properties.

## Question-2

### Private:
The code is only accessible within the same class.
### Public:
The code is accessible for all classes.
### Protected:
The code is accessible within the same class, or in a class that is inherited from that class.
### Internal:
The code is only accessible within its own assembly, but not from another assembly.
### Protected Internal:
It is used to specifies that access is limited to the current assembly or types derived from the containing class.
### Private Protected:
It is used to specifies that access is limited to the containing class or types derived from the containing class within the current assembly.

## Question-3

### Sealed Class:
Sealed classes are used to restrict the inheritance feature of object oriented programming. Once a class is defined as a sealed class, this class cannot be inherited. 
```csharp
// Sealed class  
sealed class SealedClass {  
    public int Add(int x, int y) {  
        return x + y;  
    }  
}
```

### Abstract Class:
Data abstraction is the process of hiding certain details and showing only essential information to the user. Abstraction can be achieved with either abstract classes or interfaces.
```csharp
abstract class Animal {
  public abstract void animalSound();
  public void sleep() {
    Console.WriteLine("Zzz");
  }
}
```

### Concrete Class
A concrete class is a class that has an implementation for all of its methods. They cannot have any unimplemented methods. It can also extend an abstract class or implement an interface as long as it implements all their methods. In other words, we can say that any class which is not abstract is a concrete class.
```csharp
// Concrete Class 
class Main { 
    static int product(int a, int b) { 
        return a * b; 
    } 
    static int sum(int a, int b) { 
        return a + b; 
    } 
    public static void main(String args[]) { 
        int p = product(5, 10); 
        int s = sum(5, 10); 
  
        System.out.println("Product: " + p); 
        System.out.println("Sum: " + s); 
    } 
}
```

### POCO Class
A Plain Old CLR Objects (POCO) is a class, which doesn't depend on any framework-specific base class. It is like any other normal .NET class. Due to this, they are called Plain Old CLR Objects. These POCO entities support most of the same LINQ queries as Entity Object derived entities. These POCO classes implements only the domain business logic of the Application.

## Question-4

### Object Type:
Object is a real world entity, for example, chair, car, pen etc. In other words, object is an entity that has state and behavior. Here, state means data and behavior means functionality. Object is created at runtime. Object is an instance of a class. All the members of the class can be accessed through Object.
#### Example
```csharp
Student s1 = new Student();//creating an object of Student    
```

### Dynamic Type:
It is used to avoid the compile-time type checking. The compiler does not check the type of the dynamic type variable at compile time, instead of this, the compiler gets the type at the run time. If the variable does not initialized it will not throw an error.
#### Example
```csharp
// Dynamic variables 
dynamic value1 = "HelloWorld"; 
dynamic value2 = 123234; 
dynamic value3 = 2132.55; 
dynamic value4 = false; 
```

### Anonymous Type
An anonymous type is a type (class) without any name that can contain public read-only properties only. It cannot contain other members, such as fields, methods, events, etc.
#### Example
```csharp
var student = new { Id = 1, FirstName = "James", LastName = "Bond" };
Console.WriteLine(student.Id); //output: 1
Console.WriteLine(student.FirstName); //output: James
Console.WriteLine(student.LastName); //output: Bond

student.Id = 2;//Error: cannot chage value
student.FirstName = "Steve";//Error: cannot chage value
```