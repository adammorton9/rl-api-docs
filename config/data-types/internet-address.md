---
description: Configures an input field to appear for a URL.
---

# Internet Address

Accepts a URL in the format of `http://www.url.com`.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | No                          | Yes             |

### Internet Address Data Type Definition

```json
{
     "fields" : [
     	{
	   "fieldName": "Internet URL",
            "label": "internet_url",
            "required": false,
            "maxLength": 10000,
            "editable": true,
            "dataType": "InternetAddress",
            "allowMultiple": false,
            "listOfValues": []
	},
        ...
    ]
}  
```
