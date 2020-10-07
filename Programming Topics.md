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

### Abstract Class:
Data abstraction is the process of hiding certain details and showing only essential information to the user. Abstraction can be achieved with either abstract classes or interfaces.

### Concrete Class
A concrete class is a class that has an implementation for all of its methods. They cannot have any unimplemented methods. It can also extend an abstract class or implement an interface as long as it implements all their methods. It is a complete class and can be instantiated. In other words, we can say that any class which is not abstract is a concrete class.