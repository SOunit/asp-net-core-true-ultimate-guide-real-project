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