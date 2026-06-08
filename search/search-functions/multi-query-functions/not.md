# $not

The $not function allows you to filter search results with one or more conditions and the inverse of the query must be true.  The following query would return results where the template ID is **not** equal to 1.

```json
{
    "query": {
        "$not": [
            {
                "$eq": [
                    "templateid",
                    1
                ]
            }
        ]
    },
    "rows": 0,
    "start": 100
}
```
