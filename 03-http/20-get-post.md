- get body data from post request
- body is stream, convert to string
- parse string to dictionary to use data easily
- StringValues can allow same key
  - age=20&age=30 -> age = [20, 30]

```
using System.IO;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.Run(async (HttpContext context) => {
    StreamReader reader = new StreamReader(context.Request.Body);
    string body = await reader.ReadToEndAsync();
});
```

- parse
  - to change string to dictionary type

```
using System.IO;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.Run(async (HttpContext context) => {
    StreamReader reader = new StreamReader(context.Request.Body);
    string body = await reader.ReadToEndAsync();

    // age=30&age=28 -> StringValues can handle 1 key to multiple values
    Dictionary<string, StringValues> queryDict = Microsoft.AspNetCore.WebUtilities.QueryHelper.ParseQuery(body);

    if(queryDict.ContainsKey("firstName")){
        string firstName = queryDict["firstName"][0];
        await context.Response.WriteAsync(firstName);
    }
});
```