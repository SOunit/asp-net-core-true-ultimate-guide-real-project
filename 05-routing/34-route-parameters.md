# sample url

- /files/sample.txt
- /employee/profile/john

- /files/{filename}.{extension}
- /employee/profile/{employeeName}

- sample code

```
app.UseEndpoints(endpoints => {
    endpoints.Map("files/{filename}.{extension}", async (context) => {

        string? fileName = Convert.ToString(context.Request.RouteValue["filename"]);
        string? extension = Convert.ToString(context.Request.RouteValue["extension"]);

        await context.Response.WriteAsync($"In Files {filename} - {extension}");
    });
})
```
