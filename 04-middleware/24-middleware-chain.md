# app.Use

- can pass request to subsequent middleware

```
app.Use(async (HttpContext context, RequestDelegation next) => {
    await context.Response.Write("Hello");
    await next(context);
})
```
