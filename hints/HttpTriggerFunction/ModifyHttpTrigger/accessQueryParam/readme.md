```cs
[FunctionName("HttpTriggerFunction")]
public static async Task<IActionResult> Run(
    [HttpTrigger(AuthorizationLevel.Anonymous, "get", "post", Route = null)] HttpRequest req,
    ILogger log)
{
    string name = req.Query["name"];
    string company = req.Query["company"];
    string responseMessage = $"Hello, {name}. Are you ready for this workshop with {company}?";
    return new OkObjectResult(responseMessage);
}
```
