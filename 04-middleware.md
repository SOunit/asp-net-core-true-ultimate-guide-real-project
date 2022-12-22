# middleware

- SingleResponsibility
  - easy to understand and maintenance
  - independent, no effect to other middleware if remove
- middleware process flow
  - get request, go middleware1, middleware2, middleware3, etc, send response
- benefit
  - error handling
  - authentication check
  - etc.