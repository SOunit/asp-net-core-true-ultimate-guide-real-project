# constraint sample code

```
endpoints.Map("products/details/{id:int?}", async context => {
    if(context.Request.RouteValues.ContainKey("id")){
        int id = Convert.ToInt32(context.Request.RouteValue["id"]);
        await context.Response.WriteAsync($"Product details - {id}");
    }
});
```

# constraints

- int
- bool
- datetime

# valid datetime value
- yyyy-MM-dd