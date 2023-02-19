- set null if not supplied

```
endpoints.Map("products/details/{id?}", async context => {
    int id = Convert.ToInt32(context.Request.RouteValues["id"]);
    await context.Response.WriteAsync($"Products details - {id}");
});
```
