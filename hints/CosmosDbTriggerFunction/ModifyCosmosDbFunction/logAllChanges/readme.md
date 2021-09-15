
```cs
[Function("CosmosTriggerFunction")]
public static void Run(
    [CosmosDBTrigger(
    databaseName: "storage",
    collectionName: "ratings_88a3175c-310a-45b4-920d-c0576f617e5d",
    ConnectionStringSetting = "CosmosConnection",
    LeaseCollectionName = "leases_88a3175c-310a-45b4-920d-c0576f617e5d")] 
    IReadOnlyList<Rating> input, 
    FunctionContext context)
{
    if (input != null && input.Count > 0)
    {               
        foreach (var inputObject in input)
        {
            logger.LogInformation("Document Id: " + inputObject.Id);
        }
    }    
}
```
