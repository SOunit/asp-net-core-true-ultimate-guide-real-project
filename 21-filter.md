# filter

- code block that executes before / after action method

- ResourceFilter
- ActionFilter
- ExceptionFilter
- ResultFilter

# execution flow

- request
- other middleware1
- routing middleware
  - action selection
- endpoint middleware
- other middleware2

# endpoint middleware detail

- entry
- authorization filter
  - OnAuthorization
- resource filter
  - OnResourceExecuting
- Model Binding & Validation
- Action Filter
  - OnActionExecuting
- Action Method
- Action Filter
  - OnActionExecuted
- Exception Filter
  - OnException
- ResultFilter
  - OnResultExecuting
- IActionResult
  - execution
- ResultFilter
  - OnResultExecuted
- ResourceFilter
  - OnResourceExecuted
- Exit

# setup of action filter

- add action filter class file
  - `Filters/ActionFilters/PersonsListActionFilter.cs`
- add annotation
  ```
  [TypeFilter(typeof(PersonsListActionFilter))]
  ```

# what do you do in action filter?

- validation arguments
- manipulation data

# action filter.validate

- get arguments
  ```
  if(context.ActionArguments.ContainsKey("searchBy")){
    string? searchBy = Convert.ToString(context.ActionArguments["searchBy"]);
    if(!string.IsNullOrEmpty(searchBy)){
      var searchByOptions = new List<string>(){
        nameof(PersonResponse.PersonName),
        nameof(PersonResponse.Email),
        nameof(PersonResponse.DateOfBirth),
        nameof(PersonResponse.Gender),
      }
    }
  }
  ```

# action filter points

- create filter class
- connect to action
- OnExecuted cannot get arguments
  - use `context.HttpContext.Items` to pass arguments from OnExecuting
