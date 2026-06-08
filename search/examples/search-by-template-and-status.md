---
description: >-
  Use the below search on any of the /search endpoints to filter the results by
  a specific template and status.
---

# Search by template and status

```javascript
{
    "query": {
        "$and": [
            {
                "$eq": [
                    "templateid",
                    "3"
                ]
            },
            {
                "$eq": [
                    "statusid",
                    "1"
                ]
            }
        ]
    },
    "start": 0,
    "rows": 100
}
```
