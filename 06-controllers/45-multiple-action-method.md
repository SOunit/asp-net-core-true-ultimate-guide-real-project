- add controllers

```
builder.Services.AddTransient<HomeController>();
```

- better approach

```
builder.Services.AddControllers();
```

- use `MapControllers`
  - use `UseRouting` and `UseEndpoints` internally
