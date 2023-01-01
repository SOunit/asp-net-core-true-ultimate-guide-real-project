# model binding
- binding happens by framework
- object is created by framework
- `FromQuery` limit to from query

# validation
- to avoid lengthy repeated code

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
