- add response body in ASP.NET

```
app.Run(async (HttpContext context) => {
    context.Response.Headers["MyKey"] = "My Key";
    await context.Response.WriteAsync("Hello");
})
```

- common http response headers
  - date
    - date and time of response
  - server
    - name of the server
  - content-type
    - MIME type of response body
  - content-length
  - cache-control
    - save to cache memory in browser
    - browser do not make request to server, instead get data from cache memory
  - set-cookie
  - access-control-allow-origin
  - location