- add method to external class, without modify actual class
- static method is injected to target class as instance method

  - that's why we have to pass class using this keyword

- sample

```
class ClassName{

}
```

```
static class ClassName{
    public static ReturnType MethodName(this ClassName ParameterName, ...){
        method body here
    }
}
```
