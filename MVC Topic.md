# Question-1
##  Model View Controller (MVC):
The Model View Controller (MVC) design pattern specifies that an application consist of a data model, presentation information, and control information. The pattern requires that each of these be separated into different objects.
1. **Model**
This part of the design pattern is the primary part and contains purely application information. It doesn’t contain any information on how to show the data to the user. It is independent of the user interface. It controls the logic and rules of application.

2. **View**
This part helps the user to see the model’s data. The main concern of this part is to access the model’s data. The view section uses a chart, table or diagrams to represent the information. It can also show similar data and use bar graphs and tables for different purposes. It is a visualization of information that the application contains.

3. **Controller**
Most of the work is done by the controller. It provides the support for input and converts the input to commands for the application. It is used between the model and view part. The model and the view are interconnected, so the execution is reflected in the view part.

# Question-2
## View vs. Partial View:
- **View** may have markup tags like html, body, head, title, meta etc.
- **Partial view** is specially designed to render within the view and as a result it does not contain any mark up.

# Question-3
## ViewData:
- ViewData is derived from the ViewDataDictionary class and is basically a Dictionary object i.e. Keys and Values where Keys are String while Values will be objects.
- While retrieving the data it needs to be Type Cast to its original type as the data is stored as objects.
- Data is stored as Object in ViewData.
- ViewData is used for passing value from Controller to View.
- ViewData is available only for Current Request. It will be destroyed on redirection.

#### Controler
```csharp       
public class FirstController: Controller {  
    // GET: First  
    public ActionResult Index() {  
        ViewData["Message"] = "Hello SAAD!";  
        return View();  
    }  
}  
```
#### View
```csharp       
<html>   
<head>  
    <meta name="viewport" content="width=device-width" />  
    <title>Index</title>  
</head>    
<body>  
    <div> @ViewData["Message"] </div>  
</body>    
</html> 
```
## ViewBag:
- ViewBag is a Wrapper built around ViewData.
- While retrieving, there is no need for Type Casting data.
- ViewBag is used for passing value from Controller to View.
- ViewBag is available only for Current Request. It will be destroyed on redirection.

#### Controler
```csharp       
public class FirstController: Controller {  
    // GET: First  
    public ActionResult Index() {  
        ViewBag.Message = "Hello SAAD!";  
        return View();  
    }  
}   
```
#### View
```csharp       
<html>   
<head>  
    <meta name="viewport" content="width=device-width" />  
    <title>Index</title>  
</head>    
<body>  
    <div> @ViewBag.Message </div>  
</body>    
</html> 
```
## TempData:
- TempData is derived from the TempDataDictionary class and is basically a Dictionary object i.e. Keys and Values where Keys are String while Values will be objects.
- Data is stored as Object in TempData.
- While retrieving the data it needs to be Type Cast to its original type as the data is stored as objects.
- TempData can be used for passing value from Controller to View and also from Controller to Controller.
- TempData is available for Current and Subsequent Requests. It will not be destroyed on redirection.

#### Controler
```csharp       
public class FirstController: Controller {  
    // GET: First  
    public ActionResult Index() {  
        TempData["Message"] = "Hello RAJESH!";   
         return new RedirectResult(@"~\Second\");
    }  
}
```
#### View
```csharp       
<html>   
<head>  
    <meta name="viewport" content="width=device-width" />  
    <title>Index</title>  
</head>    
<body>  
    <div> @TempData["Message"]; </div>  
</body>    
</html> 
```
