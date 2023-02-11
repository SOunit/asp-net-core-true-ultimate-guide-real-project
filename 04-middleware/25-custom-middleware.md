# custom middleware

- use `IMiddleware` interface
- add custom middleware as service to use it

```
builder.Services.AddTransient<MyCustomMiddleware>();
```

- use `useMiddleware` function

```
app.UseMiddleware<MyCustomMiddleware>();
```

- middleware class sample

```
class MiddlewareClassName: IMiddleware{
    public async Task InvokeAsync(HttpContext context, RequestDelegate next){
        // before logic
        await next(context)
        // after logic
    }
}
```
