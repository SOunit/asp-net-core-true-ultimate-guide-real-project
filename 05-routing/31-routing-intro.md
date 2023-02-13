# UseRouting, UseEndPoints

- first `UseRouting`
- only after `UseRouting`, `UseEndPoints` is available

# UseRouting

- enable routing
- select appropriate endpoints based on url path and HTTP method
- setup routing for `UseEndPoints` can work

```
app.UseRouting();
```

# UseEndPoints

- execute endpoints

```
app.UseEndPoints(endpoints => {
    endpoints.Map(...);
    endpoints.MapGet(...);
    endpoints.MapPost(...);
})
```
