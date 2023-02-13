# sample url

- /files/sample.txt
- /employee/profile/john

- /files/{filename}.{extension}
- /employee/profile/{employeeName}

- sample code

```
app.UseEndpoints(endpoints => {
    endpoints.Map("files/{filename}.{extension}", async (context) => {
        await context.Response.WriteAsync("In Files");
    });
})
```
