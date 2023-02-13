# when to use in production scenario?
- for logging, using Endpoint object and `DisplayName`
  - login log
  - etc.

# how to use GetEndPoint

- can get EndPoint object
- use after `UseRouting`
  - before, it's still `null`

```
using Microsoft.AspNetCore.Http;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

// endpoint is still null here
app.Use(async (context, next) => {
    Endpoint endpoint = context.GetEndpoint();
    await next(context);
});

// enable routing
app.UseRouting();

// endpoint is populated here
app.Use(async (context, next) => {
    Endpoint endpoint = context.GetEndpoint();
    await next(context);
});

// create endpoints
app.UseEndpoints(endpoints => {
    // add your endpoints here
    endpoints.MapGet("map1", async (context) => {
        await context.Response.WriteAsync("In Map 1");
    });
});
```