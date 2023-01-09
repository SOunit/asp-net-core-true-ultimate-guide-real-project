# summary

- create filter class
- connect to action
- OnExecuted cannot get arguments
  - use `context.HttpContext.Items` 
  - to pass arguments from OnExecuting
  - to pass data via `ViewBag`

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

# arguments

- can pass argument from controller to filter

  ```
  [TypeFilter(nameof(SomeActionFilter), Arguments = new Object[] {"arg1", "arg2"})]
  ```

  - add argument to constructor of action filter class

  ```
  public SomeActionFilter(string arg1, string arg2){
    Arg1 = arg1;
    Arg2 = arg2;
  }
  ```
