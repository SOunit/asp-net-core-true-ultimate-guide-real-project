# why

- convention
- to simplify calling middleware
- can add method to app and can call like this

```
app.UseMyCustomMiddleware();
```

# syntax

- use static class
- use method extension in C#

```
static class ClassName{
    public static IApplicationBuilder ExtensionMethodName(this IApplication app){
        return app.UseMiddleware<MiddlewareName>();
    }
}
```
