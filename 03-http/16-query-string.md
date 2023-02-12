- sample

```
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.Run(async (HttpContext context) => {
    context.Response.Headers["Content-type"] = "text/html";

    if(context.Request.Method == "GET"){
        if(context.Request.Query.ContainKey("id")){
            var id = context.Request.Query["id"];
            context.Response.WriteAsync($"<p>{id}</p>");
        }
    }
})
```
