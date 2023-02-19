# endpoint selection order

- specific, higher priority

1. url template with more segments

- `a/b/c/d` > `a/b/c`

2. literal is higher than parameter

- `a/b` > `a/{parameter}`

3. with constraints

- `a/b:int` > `a/b`

4. catch param

- `a/b` > `a/**`
