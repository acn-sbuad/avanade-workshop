```cs
[Function("HttpTriggerFunctionTask")]
public static HttpResponseData Run([HttpTrigger(AuthorizationLevel.Anonymous, "get", "post")] HttpRequestData req,
    FunctionContext executionContext)
{
    string responseString = $"The current date and time is {System.DateTime.Now}";
    return new OkObjectResult(responseString);
}
```
