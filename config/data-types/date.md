---
description: >-
  Configures a date field, allows the user to enter a date into a text box or
  choose from a date picker
---

# Date

Allows a date to be chosen via the date picker or by entering a date into the input field.\
Expects a date in the user's format, `MM/DD/YYYY`, `DD/MM/YYYY`, etc.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | No                          | Yes             |

### Date Data Type Definition

```json
{
     "fields" : [
     	{
	    "fieldName": "select date",
            "label": "select_date",
            "required": false,
            "maxLength": 10000,
            "editable": true,
            "dataType": "Date_US",
            "allowMultiple": false,
            "listOfValues": []
	},
        ...
    ]
}  
```
