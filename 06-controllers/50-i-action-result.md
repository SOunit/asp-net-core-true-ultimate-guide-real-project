# IActionResult

- interface of parent class

# benefit

- can change return type conditionally

```
public class HomeController: Controller{
    public ContentResult Index(){
        // book id should be supplied
        if(!Request.Query.ContainsKey("bookid")){
            return Content("Book id is not supplied");
        }

        // book id can't be empty
        if(string.IsNullOrEmpty(Convert.ToString(Request.Query["bookid"]))){
            return Content("book id can't be null or empty");
        }

        // book id should be between 1 to 1000
        int bookId = Convert.ToInt16(ControllerContext.HttpContext.Request.Query["bookid"]);
        if(bookId <= 0){
            return Content("book id cannot be less than 0");
        }

        if(bookId > 1000){
            return Content("book id cannot be greater than 1000");
        }

        return File("/sample.pdf", "application/pdf");
    }
}
```
