---
description: Configures a input field to appear that allows a year to be entered
---

# Four Digit Year

Configures an input that allows a 4-digit year to be entered. Regardless of max length specified only 4 digits are valid.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| 0000            | No                          | Yes             |

### Four Digit Year Data Type Definition

```json
{
     "fields" : [
     	{
	    "fieldName": "4 digit year",
	    "label": "4_digit_year",
            "required": false,
            "maxLength": 10000,
            "editable": true,
            "dataType": "FourDigitYear",
            "allowMultiple": false,
            "listOfValues": []
	},
        ...
    ]
}  
```
