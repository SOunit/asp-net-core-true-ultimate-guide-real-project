# endpoint selection order
- specific, higher priority

- url template with more segments
  - `a/b/c/d` > `a/b/c`
- literal is higher than parameter
  - `a/b` > `a/{parameter}`
- with constraints
  - `a/b:int` > `a/b`
- catch param
  - `a/b` > `a/**`