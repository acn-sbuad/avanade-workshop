# Modifying the HTTP trigger function

## Step 1: Hardcoded response

```cs
[Function("HttpTriggerFunctionTask")]
public static HttpResponseData Run(
    [HttpTrigger(AuthorizationLevel.Anonymous,"get", "post")] 
    HttpRequestData req,
    FunctionContext executionContext)
{
    var response = req.CreateResponse(HttpStatusCode.OK);
    response.Headers.Add("Content-Type", "text/plain; charset=utf-8");
    response.WriteString("Hi, Ola Nordmann. Welcome to my first Azure Function.");
    return response;
}
```
