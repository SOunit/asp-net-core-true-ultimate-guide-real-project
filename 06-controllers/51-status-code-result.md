# status code results

- StatusCodeResult
- UnauthorizedResult
- BadRequestResult
- NotFoundResult

# BadRequest

- for 400 bad request
- set status code 400 automatically

```
return BadRequest("book id can't be null or empty");
```

# NotFoundResult

- for 404 not found result
- used with database record etc.

```
return NotFound("book id can't be greater than 1000");
```

# Unauthorized

- for 401 not authorized result

```
return Unauthorized("User must be authorized");
```

# StatusCodeResult

- if above does not match
