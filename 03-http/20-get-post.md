- get body data from post request

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
        string firstName = queryDict["firstName"];
    }
});
```