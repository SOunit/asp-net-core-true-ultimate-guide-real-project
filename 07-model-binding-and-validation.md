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

# custom validation
- create new class for validation
- inherit `ValidationAttribute` class
- override `IsValid` method return type is `ValidationResult`
- ErrorMessage come from parent class `ValidationAttribute`
- SomeValidation(200, ErrorMessage = "")
  - 1st argument is defined in constructor
  - ErrorMessage comes from parent class

# custom validation for multiple inputs
- validationContext
  - ObjectInstance
    - model class is instantiate as ObjectInstance
  ```
  PropertyInfo? otherProperty = validationContext.ObjectType.GetProperty(OtherPropertyName);
  DateTime from_date = Convert.ToDateTime(otherProperty.GetValue(validationContext.ObjectInstance));
  ```
- reflection?
  - to get data using reflection in C#

# IValidatableObject
- for unique validation logic
- can put validation logic to model class
- do not need to be reusable, it's unique to the class
- inherit `Validate` method
- easy to access properties

# bind
- can select prop to bind
  - add to action method
- `BindNever` can skip binding
  - add to model prop

# FromBody
- to receive JSON
- json is enabled by default
- if you want to use XML, then you have to enable XML
  - image
    - services.controller().xmlSomething()
  - use `FromBody` to bind to model class

# Custom Model Binder
- target 1 action
- can use original binding logic
- have to bind all props manually if you use CustomModelBinder

# ModelBinderProviders
- target 1 class
  - means target all actions using the class
