# naming

- use [Controller] with any name

```
[Controller]
public class Home{
    public string Index(){
        return "Hello from Index";
    }
}
```

- follow controller convention name

```
public class HomeController{
    public string Index(){
        return "Hello from Index";
    }
}
```

# AddControllers

- enable controllers to service

# MapControllers

- enable `UseRouting` and `UseEndpoints`

# responsibility of controllers

- reading requests

  - query string
    - `some-url?key=value&key=value`
  - request body
  - request cookies
  - request headers
  - etc.

- validation
- invoke models
- preparing response
