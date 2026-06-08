---
description: Configures an input field to appear that the user can enter an input field
---

# Email

The input has automatic validation on it to ensure that valid email addresses are entered.

`"allowMultiple"` can be set to true to allow more than one email to be entered

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | Yes                         | Yes             |

### Email Data Type Definition

```json
{
     "fields" : [
     	{
	    "fieldName": "User Email",
            "label": "user_email",
            "required": false,
            "maxLength": 10000,
            "editable": true,
            "dataType": "Email",
            "allowMultiple": false,
            "listOfValues": []
	},
        ...
    ]
}  
```
