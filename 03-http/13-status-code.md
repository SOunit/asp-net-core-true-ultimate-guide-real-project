- can assign status code to response header

```
app.Run(async (HttpContext context)=>{
    context.Response.StatusCode = 500;
    context.Response.WriteAsync("Hello");
})
```

