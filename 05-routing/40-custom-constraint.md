# custom route constraint class

- good for reuse constraint

```
public class ClassName: IRouteConstraint {
    public bool Match(HttpContext? HttpContext, IRouter? route, string routeKey, RouteValueDictionary values, RouteDirection routeDirection){
        // return true or false
    }
}
```

```
builder.Services.AddRouting(options => {
    options.ConstraintMap.Add("name", typeof(ClassName));
}); // adding the custom constraint to routing
```

- sample

```
endpoints.Map("sales-report/{year:int:min(1900)}/{month:months}")
```

```
builder.Services.AddRouting(options => {
    options.ConstraintMap.Add("months", typeof(MonthsCustomConstraint))
})
```

```
public class MonthsCustomConstraint: IRouteConstraint{
    public bool Match(HttpContext? httpContext, IRouter? route, string routeKey, RouteValueDictionary values, RouteDirection routeDirection){
        // check whether the value exists
        if(!values.ContainsKey(routeKey)){
            return false;   // not a match
        }

        Regex regex = new Regex("^(apr|jul|oct|jan)$");
        string? monthValue = Convert.ToString(values[routeKey]);

        if(regex.IsMatch(monthValue)){
            return true; // it's a match
        }

        return false;
    }
}
```
- values = [{key: value}, {key: value}, ...]
  - [{year: 1990}, {month: january}]
- routeKey
  - routeKey = month