# app.run()

- do not forward the request to next middleware

```
app.Run(async(HttpContext context) => {
    await context.Response.WriteAsync("hello");
})
```
