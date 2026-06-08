# $and

The $and function allows you to filter search results with one or more conditions and all conditions must be true.  The following query would return results where the template ID is 1 **and** the start\_date characteristic has a value greater than 2018-03-15.

```json
{
    "query": {
        "$and": [
            {
                "$eq": [
                    "templateid",
                    1
                ]
            },
            {
                "$gt": [
                    "start_date",
                    "2018-03-15"
                ]
            }
        ]
    },
    "rows": 0,
    "start": 100
}
```
