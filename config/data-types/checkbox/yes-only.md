---
description: >-
  A Yes only checkbox can specified that will only toggle to Yes when checked
  and nothing when unchecked.
---

# Yes only

To create a Yes Only checkbox, create an LOV called Yes (only) with solely the value “Yes.” This will result in a checkbox with only the Yes option.

```jsonp
{
     "fields": [
        {
           "fieldName": "Yes Only",
            "label": "yes_only",
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
                }
            ]
        },
        ...
    ]
}
```
