# Search for all records that don't have a value for a specific field

If the records that are needed from a query are all of those where a specific characteristic hasn't been populated, the query needs to combine a $not query with a $range query where the range is all possible values ( \* TO \* ). For example, to find all rights that don't have an **end\_date** set:&#x20;

```
POST - https://ris.rightsline.com/v4/right/search
{
    "query": {
        "$not": [
            {
                "$range": [
                    "end_date",
                    "*",
                    "*"
                ]
            }
        ]
    }
}
```
