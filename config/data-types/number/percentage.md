---
description: Similar to Number, input field will represent a percent.
---

# Percentage

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | No                          | No              |

### Percentage Data Type Definition

```json
{
     "fields" : [
     	{
	   "fieldName": "Input Percent",
            "label": "input_percent",
            "required": false,
            "maxLength": 10000,
            "editable": true,
            "dataType": "Percentage",
            "allowMultiple": false,
            "listOfValues": []
	},
        ...
    ]
}  
```
