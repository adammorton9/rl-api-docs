---
description: Configures a number input field
---

# Number

Expects only numbers to be input. This field does allow decimal numbers to be input, up to any number of decimal places.

Performs validation to ensure only numbers are valid input. Honors the `"maxLength"` setting.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | No                          | No              |

### Number Data Type Definition

```json
{
     "fields" : [
     	{
	   "fieldName": "Input Number",
            "label": "input_number",
            "required": false,
            "maxLength": 10000,
            "editable": true,
            "dataType": "Number",
            "allowMultiple": false,
            "listOfValues": []
	},
        ...
    ]
}  
```
