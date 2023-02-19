- can assign default parameter

```
endpoints.Map("employee/profile/{EmployeeName=jack}", async(context)=>{
     string? employeeName = Convert.ToString(context.Request.RouteValue["employeeName"]);
     await context.Response.WriteAsync($"In Employee profile - {employeeName}");
});
```
