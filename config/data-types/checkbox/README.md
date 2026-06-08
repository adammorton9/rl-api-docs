---
description: Allows a checkbox to appear for use as a Yes or Yes/No field.
---

# Checkbox

A Value Set and a Value Source are required, just like with List of Value Characteristics, but instead of a dropdown appearing on the record, there will be a checkbox.\
\
Choose Yes/No as your Value Set to make a Yes/No checkbox. This will create a checkbox that will toggle between Yes and No when clicked.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | No                          | No              |

### Checkbox Data Type Definition

```json
{
     "fields" : [
     	{
		"fieldName": "Checkbox single",
		"label": "checkbox_single",
		"required": false,
		"maxLength": 10000,
		"editable": true,
		"dataType": "Checkbox",
		"allowMultiple": false,
		"listOfValues": [
		    {
		       "id": 1,
		       "label": "Yes",
		       "xref": null,
		       "childValues": []
		    },
		    {
		       "id": 2,
		       "label": "No",
		       "xref": null,
		       "childValues": []
		    }
	      ]
	},
        ...
    ]
}  
```
