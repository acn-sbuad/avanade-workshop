```cs
[Function("HttpTriggerFunctionTask")]
public static HttpResponseData Run([HttpTrigger(AuthorizationLevel.Anonymous, "get", "post")] HttpRequestData req,
    FunctionContext executionContext)
{
    var response = req.CreateResponse(HttpStatusCode.OK);
    response.Headers.Add("Content-Type", "text/plain; charset=utf-8");
    
    var query = HttpUtility.ParseQueryString(req.Url.Query);
    string company  = query["company"];
    
    string res = !string.IsNullOrEmpty(company) ? $"You provided company: {company}" : "Please include a company in query.";
    
    response.WriteString(res);
    return response;
}
```
