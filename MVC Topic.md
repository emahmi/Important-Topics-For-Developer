# Question-1
##  Model View Controller (MVC):
The Model View Controller (MVC) design pattern specifies that an application consist of a data model, presentation information, and control information. The pattern requires that each of these be separated into different objects.
- **Model**
This part of the design pattern is the primary part and contains purely application information. It doesn’t contain any information on how to show the data to the user. It is independent of the user interface. It controls the logic and rules of application.

- **View**
This part helps the user to see the model’s data. The main concern of this part is to access the model’s data. The view section uses a chart, table or diagrams to represent the information. It can also show similar data and use bar graphs and tables for different purposes. It is a visualization of information that the application contains.

- **Controller**
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
        TempData["Message"] = "Hello SAAD!";   
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
# Question 4
## Action Result:
Action Result is a result of action methods or return types of action methods. Action result is an abstract class. It is a base class for all type of action results.

#### Example
```csharp   
namespace System.Web.Mvc  
{  
    public abstract class ActionResult  
    {  
        //  
        // Summary:  
        //     Initializes a new instance of the System.Web.Mvc.ActionResult class.  
        protected ActionResult();  
    }  
}
```
### Types of Action Results:
- **Partial View Result** is returning the result to Partial view page. Partial view is one of the views that we can call inside Normal view page.

- **Redirect result** is returning the result to specific URL. It is rendered to the page by URL. If it gives wrong URL, it will show 404 page errors.

- **Redirect to Action result** is returning the result to a specified controller and action method. Controller name is optional in Redirect to Action method. If not mentioned, Controller name redirects to a mentioned action method in current Controller. Suppose action name is not available but mentioned in the current controller, then it will show 404 page error.

- **Json result** is a significant Action Result in MVC. It will return simple text file format and key value pairs. If we call action method, using Ajax, it should return Json result.

- **File Result** returns different file format view page when we implement file download concept in MVC using file result. 

- **Content result returns** different content's format to view. MVC returns different format using content return like HTML format, Java Script format and any other format.

[Click here to see examples](https://www.c-sharpcorner.com/article/different-types-of-action-results-in-asp-net-mvc/)


# Question-5
## DataAnnotations:
Data annotations are attributes that can be applied to classes or class members to specify the relationship between classes, describe how the data is to be displayed in the UI, and specify validation rules. 
#### Example
```csharp
public class Student  {
  
   [ScaffoldColumn(false)]  
   publicintStudentID { get; set; }  
   [DataType(DataType.Text)]  
   [Required(ErrorMessage = "Please enter name"), MaxLength(30)]  
   [Display(Name = "Student Name")]  

   public string Name { get; set; }  
   [MaxLength(3),MinLength(1)]  
   [Required(ErrorMessage = "Please enter marks")]  

   publicint Marks { get; set; }  
   [DataType(DataType.EmailAddress)]  
   [Required(ErrorMessage = "Please enter Email ID")]  
   [RegularExpression(@"^\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$", ErrorMessage = "Email is not valid.")]  

   public string Email { get; set; }  
   [Required(ErrorMessage = "Please enter department")]  

   public string Department { get; set; }  
   [Required(ErrorMessage = "Please enter Mobile No")]  
   [Display(Name = "Contact Number")]  
   [DataType(DataType.PhoneNumber)]  
   public int Mobile { get; set; }  
}
```
# Question-6
## Filter Attributes:
Filters are custom classes that provide both a declarative and programmatic means to add pre-action and post-action behavior to controller action methods.
- **Authorization filters** performs authentication and authorizes before executing an action method.
- **Action filters** performs some operation before and after an action method executes.   
- **Result filters** performs some operation before or after the execution of the view.
- **Exception filters** performs some operation if there is an unhandled exception thrown during the execution of the ASP.NET MVC pipeline.
