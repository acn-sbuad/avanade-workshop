```cs
[Function("HttpTriggerFunctionTask")]
public static HttpResponseData Run([HttpTrigger(AuthorizationLevel.Anonymous, "get", "post")] HttpRequestData req,
    FunctionContext executionContext)
{
    var response = req.CreateResponse(HttpStatusCode.OK);
    response.Headers.Add("Content-Type", "text/plain; charset=utf-8");
    response.WriteString($"The current time is: {DateTime.Now.ToString()}");
    return response;
}
```
