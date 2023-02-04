# app.Use

- can pass request to subsequent middleware

```
// middleware1
app.Use(async (HttpContext context, RequestDelegation next) => {
    await context.Response.Write("Hello");
    await next(context);
})

// middleware2, terminating middleware
app.Use(async (HttpContext context, RequestDelegation next) => {
    await context.Response.Write("Hello");
})

// middleware3
app.Use(async (HttpContext context, RequestDelegation next) => {
    await context.Response.Write("Hello");
    await next(context);
})
```
