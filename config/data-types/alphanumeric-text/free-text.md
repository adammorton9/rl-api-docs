---
description: >-
  Alpha Numeric allows plain text of alphabetic or mixed numeric/alpha data to
  be entered into the text field. For example, a “Notes” field.
---

# Free text

* "allowMultiple" can be set to true, will allow multiple input entries from the user.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| -               | Yes                         | Only on length  |

### Free Text Data Type Definition

```json
{
     "fields": [
        {
            "fieldName": "Notes",
            "label": "notes",
            "required": false,
            "maxLength": 5000,
            "editable": true,
            "dataType": "AlphaNumericText",
            "allowMultiple": true,
            "listOfValues": []
        },
        ...
    ]
}  
```
