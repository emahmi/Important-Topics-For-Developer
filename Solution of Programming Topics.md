# Question-1 

### Class
A class is like a blueprint of a specific object. In object-oriented programming, a class defines some properties, fields, events, methods, etc. A class defines the kinds of data and the functionality their objects will have. A class enables you to create your custom types by grouping variables of other types, methods, and events.

### Enum
An enum lets you declare a series of identifiers for use in your code. The compiler replaces them with numbers for you. It's often useful for making your code more readable and maintainable, because you can use descriptive names without the performance penalty of string comparisons. 

### Struct
A struct contains zero or more pieces of data (variables or objects), grouped together so they can be stored, processed, or passed as a single unit. A struct can be a lot more complex though. It's actually exactly the same as aclass, except that members are public by default instead of private. Like a class, a struct can have member functions and template parameters and so on.

### Interface
An interface can be defined using the interface keyword. An interface can contain declarations of methods, properties, indexers, and events. However, it cannot contain fields, auto-implemented properties.

# Question-2

- ***Private:*** The code is only accessible within the same class.
- ***Public:*** The code is accessible for all classes.
- ***Protected:*** The code is accessible within the same class, or in a class that is inherited from that class.
- **Internal:*** The code is only accessible within its own assembly, but not from another assembly.
- ***Protected Internal:*** It is used to specifies that access is limited to the current assembly or types derived from the containing class.
- ***Private Protected:*** It is used to specifies that access is limited to the containing class or types derived from the containing class within the current assembly.

# Question-3

### Sealed Class:
Sealed classes are used to restrict the inheritance feature of object oriented programming. Once a class is defined as a sealed class, this class cannot be inherited. 

#### Example
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

#### Example
```csharp
// Abstract Class
abstract class Animal {
  public abstract void animalSound();
  public void sleep() {
    Console.WriteLine("Zzz");
  }
}
```
### Concrete Class
A concrete class is a class that has an implementation for all of its methods. They cannot have any unimplemented methods. It can also extend an abstract class or implement an interface as long as it implements all their methods. In other words, we can say that any class which is not abstract is a concrete class.

#### Example
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

# Question-4

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
var student = new { Id = 1, FirstName = "James", LastName = "Bond" }; // Anonymous variable
Console.WriteLine(student.Id); //output: 1
Console.WriteLine(student.FirstName); //output: James
Console.WriteLine(student.LastName); //output: Bond

student.Id = 2;//Error: cannot chage value
student.FirstName = "Steve";//Error: cannot chage value
```
### Anonymous Function / Method
#### Example
```csharp		
// Anonymous Method using delegate keyword
public class Program{
	public delegate void Print(int value);	
	public static void Main(){
		Print newObj = delegate(int val) { 
				Console.WriteLine("Inside Anonymous value: {0}", val); // Output: "Inside Anonymous value: 10011"
			};
    	newObj(10011); 
	}
}
```

# Question-5

### Lambda Expression
Lambda expressions in C# are used like anonymous functions, with the difference that in Lambda expressions you don’t need to specify the type of the value that you input thus making it more flexible to use.
#### Example
```csharp		
public static void Main(){  
        List<int> list = new List<int>() { 1, 2, 3, 4, 5, 6 };  
        List<int> evenNumbers = list.FindAll(x => (x % 2) == 0);  // It gives all even numbers
} 
```

### Events
Events are user actions such as key press, clicks, mouse movements, etc., or some occurrence such as system generated notifications. Applications need to respond to events when they occur. For example, interrupts. Events are used for inter-process communication.
#### Example
```csharp		
//Declare a delegate and then declare a variable of the delegate with event keyword.
public delegate void Notify();  // delegate
                    
public class ProcessBusinessLogic
{
    public event Notify ProcessCompleted; // event

}
```

### Delegate
C# Delegates are similar to pointers to functions, in C or C++. A delegate is a reference type variable that holds the reference to a method. The reference can be changed at runtime.
#### Example
```csharp		
// Delegate Syntax
[access modifier] delegate [return type] [delegate name]([parameters])
public delegate void MyDelegate(string msg);
```
#### Types of Delegates:
- SingleCast Delegate
- MultiCast Delegate
- Generic Delegate

***SingleCast Delegate:*** SingleCast Delegates refer to a single method with matching signature at a time. SingleCast Delegates derive from the System.Delegate class

***MultiCast Delegate:*** This is a kind of delegates that can refer to multiple methods that have the same signature at one time.

***Generic Delegate:*** These delegates are instantiated when needed for a specific type provided as parameters. In other words, a Generic allows you to write a class or method that can work with any data type.

#### Types of Generic Delegates:
- Func
- Action
- Predicate

# Question-6

### Generics Collection:
Generic collections hold elements of same datatypes. Generic collections (List<T>, Dictionary<T, U>, SortedList<T, U>, Queue<T> etc) store elements internally in arrays of their actual types and so no boxing or casting is ever required. Generic collections are faster than non-generic collection when using value types and more convenient when using reference types.
Example: List, Dictionary, Hashset.

- ***Dictionary:*** Dictionary is a collection of keys and values in C#. Dictionary <TKey, TValue> is included in the System.Collection.Generics namespace.
- ***Hashset:*** HashSet in C# eliminates duplicate strings or elements in an array. In C#, it is an optimized set collection.

#### Example
```csharp		
// Generic Class with Multiple Type Parameters
class KeyValuePair<TKey, TValue>
{
    public TKey Key { get; set; }
    public TValue Value { get; set; }
}
```

### Non-Generics Collection:
Non-generic collections hold elements of different datatypes. In the .NET Framework, the non-generic collections (ArrayList, Hashtable, SortedKist, Queue etc.) store elements internally in 'object' arrays which, can of course, store any type of data.Generic collections are bit slower than non-generic collection when using value types and not much convenient when using reference types.

####Examples
- ***ArrayList:*** It represents ordered collection of an object that can be indexed individually. ArrayList is an alternative to an array. However, unlike array you can add and remove items from a list at a specified position using an index and the array resizes itself automatically.

- ***BitArray:*** It represents an array of the binary representation using the values 1 and 0. It is used when you need to store the bits but do not know the number of bits in advance.

# Question-7

### Interface ICollection:
The ICollection interface in C# defines the size, enumerators, and synchronization methods for all nongeneric collections. It is the base interface for classes in the System.Collections namespace.

#### Example
```csharp		
public interface ICollection : IEnumerable      // without parameters
public interface ICollection<T>: IEnumerable    // with parameters
```

### Interface IEnumerable:
The IEnumerable<T> is used to iterate a read only collection. It has only one method GetEnumeartor() which allows you to iterate the read-only collection using a foreach loop. It only iterates in the forward direction. IEnumerable <T> is defined in as follows:

#### Example
```csharp		
// implementation of the GetEnumerator()
public interface IEnumerable<out T> : IEnumerable {
    //Returns an ienumerator that iterate through the collection.
    IEnumerator<T> GetEnumerator();
}
``` 
### Interface IQueryable:
IQueryable<T> allows you to execute a query against a specific data source wherein type of data is not specified.
This works for read-only access to a collection that implements that IEnumerable can be used with a foreach statement.

#### Example
```csharp       
public interface IQueryable : IEnumerable {
    Type ElementType { get; }
    Expression Expression { get; }
    IQueryprovider Provider { get; }
}
```
### Interface IList:
The IList interface has a non-generic collection of objects that can be individually accessed by index. IList has some properties i.e. Count, isReadOnly, Add(Obj), InddexOf(Obj) etc.

#### Example
```csharp       
public interface IList<T> : ICollection<T>, IEnumerable<T>, IEnumerable {
    T this[int index] { get; set; }
    int IndexOf(T item);
    void Insert(int index, T item);
    void RemoveAt(int index);
}
```
# Question-8

### Extension Methods:
Extension methods, as the name suggests, are additional methods. Extension methods allow you to inject additional methods without modifying, deriving or recompiling the original class, struct or interface. Extension methods can be added to your own custom class, .NET framework classes, or third party classes or interfaces.

#### Example
```csharp       
int i = 10;
// IsGreaterThan() is extension method
bool result = i.IsGreaterThan(100); // checking 10 > 100, then returns false 
```
## Question-9

### LINQ:
LINQ (Language Integrated Query) is uniform query syntax in C# and VB.NET to retrieve data from different sources and formats. It is integrated in C# or VB, thereby eliminating the mismatch between programming languages and databases, as well as providing a single querying interface for different types of data sources.

### LINQ to Object:
The LINQ to Objects provides a new way to get the data from the collections with LINQ Queries, but before that, there is a need to write a lot of foreach loops to get the data from the collections. There are also many advantages of LINQ to Objects over traditional foreach loops like more readability, powerful filtering, capability of grouping, enhanced ordering with minimal application coding.


# Question-10
### ADO.NET
ADO.NET provides a bridge between the front end controls and the back end database. The ADO.NET objects encapsulate all the data access operations and the controls interact with these objects to display data, thus hiding the details of movement of data.

#### Types of ADO.NET
- ***SQLConnection:*** It is used to establish an open connection to the SQL Server database. It is a sealed class so that cannot be inherited.

#### Example
```csharp       
using (SqlConnection connection = new SqlConnection(connectionString)) {    
    connection.Open();         
} 
```

- ***SQLCommand:*** This class is used to store and execute SQL statement for SQL Server database. It is a sealed class so that cannot be inherited.

#### Example
```csharp       
static void Main(string[] args) {  
            new Program().CreateTable();  
        }  
        public void CreateTable() {  
            SqlConnection connection = null;  
            try {  
                // Creating Connection  
                connection = new SqlConnection("data source=.; database=student; integrated security=SSPI");  
                // writing sql query  
                SqlCommand command = new SqlCommand("select * from student", connection);  
                // Opening Connection  
                connection.Open();  
                // Executing the SQL query  
                SqlDataReader dataReader = command.ExecuteReader();  
                while (dataReader.Read()) {  
                    Console.WriteLine(dataReader["name"]+" "+ dataReader["email"]);  
                }  
            }  
            catch (Exception e) {  
                Console.WriteLine("OOPs, something went wrong." + e);  
            }  
            // Closing the connection  
            finally {  
                connection.Close();  
            }  
        }  
```
- ***SQLDataReader:*** This class is used to read data from SQL Server database. It reads data in forward-only stream of rows from a SQL Server database. it is sealed class so that cannot be inherited. It inherits DbDataReader class and implements IDisposable interface.
    
- ***SQLDataAdapter:*** The DataAdapter works as a bridge between a DataSet and a data source to retrieve data. DataAdapter is a class that represents a set of SQL commands and a database connection. It can be used to fill the DataSet and update the data source.

#### Example
```csharp       
namespace DataSetExample  
{  
    public partial class DataSetDemo : System.Web.UI.Page  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            using (SqlConnection con = new SqlConnection("data source=.; database=student; integrated security=SSPI"))  
            {  
                SqlDataAdapter sde = new SqlDataAdapter("Select * from student", con);  
                DataSet ds = new DataSet();  
                sde.Fill(ds);  
                GridView1.DataSource = ds;  
                GridView1.DataBind();  
            }  
        }  
    }  
}  
```
- ***Dataset:*** It is used to fetch data without interacting with a Data Source that's why, it also known as disconnected data access method. It is an in-memory data store that can hold more than one table at the same time.
- ***DataTable:*** DataTable represents relational data into tabular form. ADO.NET provides a DataTable class to create and use data table independently. It does not have schema. We can create table schema by adding and constraints to the table.
- ***DataColumn:*** The DataColumn object represents a column of a DataTable. It allows us to add data column to the DataColumnCollection using its Add method.
- DataRow: The DataCRow object represents rows of a DataTable. It allows us to add data column to the DataRowCollection using its Add method.

#### Example
```csharp       
public partial class DataTableForm : System.Web.UI.Page {  
        protected void Page_Load(object sender, EventArgs e) {  
            DataTable table = new DataTable();  
            table.Columns.Add("ID");  
            table.Columns.Add("Name");  
            table.Rows.Add("101", "Rameez","rameez@example.com");  
            table.Rows.Add("102", "Sam Nicolus", "sam@example.com");  
            GridView1.DataSource = table;  
            GridView1.DataBind();  
        }  
    }  
```

#### Example
```csharp       

```

#### Example
```csharp       

```

#### Example
```csharp       

```

#### Example
```csharp       

```

#### Example
```csharp       

```

#### Example
```csharp       

```

#### Example
```csharp       

```
