# model binding

- binding happens by framework
- object is created by framework
- `FromQuery` limit to from query

# validation

- to avoid lengthy repeated code

# validation execution order
- request
- model binding
  - create object
  - bind value to object property
- model validation
- controller action


# model props

- IsValid
- Values
  ```
  string errors = string.Join("\n", ModelState.Values
    .SelectMany(value => value.Errors)
    .Select(error => error.ErrorMessage))
  ```
- ErrorCount

# validation annotations

- Required

```
[Required(ErrorMessage = "{0} is required")]
```

- Display

```
[Display(Name = "Property Name")]
```

- StringLength
```
[StringLength(40, MinimumLength = 3, ErrorMessage = "{0} should be between {2} and {1} characters length")]
```
- 1st = prop name
- 2nd = max-length = 40
- 3rd = min-length = 3

- Range
  - for number
  ```
  [Range(0, 999.99, ErrorMessage = "{0} should be between ${1} and ${2}")]
  ```

- Regular Expression
- EmailAddress
- Phone
- Compare
- ValidateNever