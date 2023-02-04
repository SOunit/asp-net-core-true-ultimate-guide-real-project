# create service
- create `class library`
- add service class
  `CitiesService` class
- add dependency to class library
- add service as member to controller

# DI / Dependency Injection
- should not instantiate service in controller
- why DI?
  - other developer may create service
    - so that developer1 and developer2 can work separately
  - may change in the future
    - avoid dependency for no change

# create DI
- create class library
  - `ServiceContracts`
    - `ICitiesService`

# IoC / Inversion of Control
- don't call directly, we'll call
  - `IoC Container` instantiate class

# FromServices
- can add DI to action method using `FromServices`

# Transient, Scoped, Singleton services
- Transient
  - per injection
- Scoped
  - per scope
    - browser request
- Singleton
  - for entire application lifetime


# when to use what
- Singleton
  - when service uses no state
    - using cache
    - using no memory
    - having common data
- Scoped
  - db access with EntityFramework
    - open db access per request
- Transient
  - for per controller data
    - encrypt data
    - email, unique to request

# service scope
- rootScope
- requestScope
- childScope
  - IDisposable
    - close db connection in dispose function

# add service shortcut methods
- AddTransient
  - transient service
  ```
  builder.Services.AddTransient<IService, Service>();
  ```
- AddScoped
- AddSingleton

# View Injection
- you can inject service class to View
  - View is class file compiled to html
  ```
  @inject IService service;
  ```

# Best Practice of DI
- global state in services
  - avoid using static class to store common data
  - can use `Singleton` only in simple scenario
  - use `Distributed Cache` or `Redis` for complex scenario
- request state in services
  - avoid using scoped services to share data among services
    - NOT thread-safe
  - use `HttpContext.Items`