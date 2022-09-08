```cs
[FunctionName("HttpTriggerFunction")]
public static async Task<IActionResult> Run(
    [HttpTrigger(AuthorizationLevel.Anonymous, "get", "post", Route = null)] HttpRequest req, 
    ILogger log)
{
    string name = req.Query["name"];
    
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    dynamic data = JsonConvert.DeserializeObject(requestBody);
    
    name = name ?? data?.name;

    if (!string.IsNullOrEmpty(name))
    {
        return new OkObjectResult($"Hello, {name}. This HTTP triggered function executed successfully.");
    }

    return new OkObjectResult("Welcome to my first Azure Function!");
}
```
