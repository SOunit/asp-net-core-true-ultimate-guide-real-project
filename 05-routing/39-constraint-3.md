# constraints

- characters

  - minlength(value)
  - maxlength(value)
  - length(min, max)

  - sample endpoint
  - `users/{username:length(3, 4)}`

- numbers

  - length(value)
  - min(value)
  - max(value)
  - range(min, max)

- multiple constraints

  - `products/{id:int:min(1):max(100)}`
  - `products/{id:int:range(1, 100)}`

- :alpha
- regex(expression)
