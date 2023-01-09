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