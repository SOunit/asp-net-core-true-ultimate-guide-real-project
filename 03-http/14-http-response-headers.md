- add response body in ASP.NET

```
app.Run(async (HttpContext context) => {
    context.Response.Headers["MyKey"] = "My Key";
    await context.Response.WriteAsync("Hello");
})
```
