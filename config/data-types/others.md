---
description: A few other data types that are available but not entirely built out.
---

# Others

## Password

Configures a regular text input field that allows user input. Does NOT function similar to an HTML password field.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | No                          | Only on length  |

### Password Data Type Definition

```json
{
     "fields" : [
     	{
	   "fieldName": "Pass Word",
	   "label": "pass_word",
	   "required": false,
	   "maxLength": 10000,
	   "editable": true,
	   "dataType": "Password",
	   "allowMultiple": false,
	   "listOfValues": []
	},
        ...
    ]
}  
```

## Credit Card

Configures a regular text input field that allows user input. Does NOT validate a credit card number nor does it prohibit alpha character input.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | No                          | Only on length  |

### Credit Card Data Type Definition

```json
{
     "fields" : [
     	{
	   "fieldName": "Credit Card",
	   "label": "credit_card",
	   "required": false,
	   "maxLength": 10000,
	   "editable": true,
	   "dataType": "CreditCard",
	   "allowMultiple": false,
	   "listOfValues": []
	},
        ...
    ]
}  
```
