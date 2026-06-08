---
description: Search requests return paginated results.
---

# Pagination

The API "search" endpoints return a result set of objects matching the parameters of the search request.  Rightsline utilizes offset pagination to dictate the number of objects returned in each request.  Pagination is controlled using the following two request parameters: `start`, `rows`.

## Parameters

| start | int | 0  | The zero-based index offset of the first object in the result set. |
| ----- | --- | -- | ------------------------------------------------------------------ |
| rows  | int | 25 | The number of objects to return in the result set. Max = 100       |

#### Example: Search for catalog items with a template ID = 1 (paginated)

```javascript
{
    "query": {
        	"$and": [
            {
                "$eq": [
                    "templateid",
                    1
                ]
            }
        ]
    },
    "start": 0,
    "rows": 100
}
```
