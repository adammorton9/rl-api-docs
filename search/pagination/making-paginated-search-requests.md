# Making paginated search requests

In order to retrieve all objects from a search request, we recommend the following approach:

1. Send a search request where `start = 0`, and `rows = 100`.
2. The search result will contain a property called `numFound`.  If `start` + `rows`  < `numFound`, then there are additional records to retrieve.  If this is the case, increment the start parameter by the value of the rows parameter.  For instance, if `numFound = 200`, then add 100 to 0 and assign this value to `start`  and make an additional search request, this time with `start = 100` and `rows = 100`.&#x20;
3. Repeat step 2 until `start` + `rows` >= `numFound`.  When this is the case, you have retrieved all relevant records for your search request.

#### .NET C# Example

```csharp
public IEnumerable<Entity> SendPaginatedSearchRequest(SearchRequest request)
{
    var entities = new List<Entity>();
    bool isAdditionalRecords = true;
    
    while(isAdditionalRecords)
    {
        var result = SendSearchRequest(request);
        entities.AddRange(result.Entities);
        
        if (request.Start + request.Rows < result.NumFound)
        {
            // Additional records to retrieve. Increment start by rows.
            request.Start += request.Rows;
        }
        else
        {
            // All records have been retrieved.
            isAdditionalRecords = false;
        }
    }
    return entities;
}
```
