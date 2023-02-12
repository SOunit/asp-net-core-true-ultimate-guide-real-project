- no interface implementation, `IMiddleware`
- receive `next` as constructor argument

```
class MiddlewareClassName{
    private readonly RequestDelegate _next;
    
    public MiddlewareClassName(RequestDelegate next){
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context){
        // before logic

        await _next(context);

        // after logic
    }
}
```
