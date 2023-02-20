- add controllers

```
builder.Services.AddTransient<HomeController>();
```

- better approach

```
builder.Services.AddControllers();
```

- use `MapControllers`

  - use `UseRouting` and `UseEndpoints` internally

- multiple route

```
public class HomeController{
    [Route("home")]
    [Route("/")]
    public string Index(){
        return "Hello from Index";
    }

    [Route("about")]
    public string About(){
        return "Hello from About";
    }

    [Route("contact-us/{mobile:regex(^\\d{{10}}$)}")]
    public string Contact(){
        return "Hello from Contact";
    }
}
```
