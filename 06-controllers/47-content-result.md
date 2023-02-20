# ContentResult

- can represent almost all MIME types of content
  - text/plain
  - text/html
  - application/json
  - application, xml
  - application/pdf
  - etc.

# benefit

- if return type is string, you have to setup request-header manually
- using `ContentResult` class, setup automatically.

```
public class HomeController{
    public ContentResult Index(){
        return new ContentResult(){
            Content = "Hello from Index",
            ContentType = "text/plain"
        };
    }
}
```

# better approach

- use Content method in Controller class from microsoft

```
public class HomeController: Controller {
    [Route("home")]
    [Route("/")]
    public ContentResult Index(){
        // set content, content-type
        return Content("Hello from Index", "text/plain");
    }
}
```