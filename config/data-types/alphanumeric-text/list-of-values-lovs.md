---
description: >-
  Lists of Values are sets of data that are pre-configured to be the only
  possible answers in a given field. These can be set up in a hierarchical or
  straight-line fashion.
---

# List of Values (LOVs)

Alpha Numeric Data Type is also used in conjunction with a List of Values. Lists of Values are sets of data that are pre-configured to be the only possible answers in a given field. These can be configured in a few ways:

* Single Select: Allows the user to to select one value from a pre-determined list.
  * set '"allowMultiple" to false
* Multi-select: Allows the user to select multiple values from pre-determined list.
  * set "allowMultiple" to true
* Multi-Select Hierarchal: Allows the user to select multiple values from pre-determined list of values that have been structured in a hierarchal order.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | Yes                         | Only on length  |

### List of Values Data Type Definition

```json
{
     "fields": [
        {
               "fieldName": "Alphanumeric Multi Select",
		"label": "alphanumeric_multi_select",
		"required": false,
		"maxLength": 10000,
		"editable": true,
		"dataType": "AlphaNumericText",
		"allowMultiple": true,
		"listOfValues": [
		   {
			"id": 1,
			"label": "1125",
			"xref": null,
			"childValues": []
		   },
		   {
			"id": 3,
			"label": "320",
			"xref": null,
			"childValues": []
		   },
		   { 
			"id": 2,
			"label": "96",
			"xref": null,
			"childValues": []
		   }
	    ]
        },
        ...
    ]
}
```

<br>
