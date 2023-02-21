# Json format

- difficult format in C#
- use shortcut

```
var json = "{\"key\": \"value\"}";
```

# JsonResult

- shortcut

```
var person = new Person(){
    Name = "test name"
};


return new JsonResult(person);
```

# Json

- shortcut

```
var person = new Person(){
    Name = "test name"
};

return Json(person);
```
