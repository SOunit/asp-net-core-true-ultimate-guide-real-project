- Map
  - receive any method

- MapGet
  - only get method

- MapPost
  - only post method

```
app.UseEndPoints(endpoints => {
    endpoints.Map("map", async (context) => {
        await context.Response.WriteAsync("In Map");
    });
    
    endpoints.MapGet("map-get", async (context) => {
        await context.Response.WriteAsync("In Map Get");
    });

    endpoints.MapPost("map-post", async (context) => {
        await context.Response.WriteAsync("In Map Post");
    });
});

app.Run(async context => {
    await context.Response.WriteAsync($"Request received at ${context.Request.Path}");
});
```