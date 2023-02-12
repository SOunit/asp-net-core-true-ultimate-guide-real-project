- context object
  - contains all request headers data

```
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.Run(async (HttpContext context) => {
    string path = context.Request.Path;
    string method = context.Request.Method;

    if(path == 'some-path'){
        // do this
    }else{
        // do that
    }

    context.Response.Headers["Content-type"] = "text/html";

    await context.Response.WriteAsync($"<p>{path}</p>");
    await context.Response.WriteAsync($"<p>{method}</p>");
})
```
