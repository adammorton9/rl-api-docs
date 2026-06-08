---
description: The different data types that can specified for a characteristic
---

# Data types

Data Types are defined within a template which is then associated with a record. Within the Rightsline app there is the ability to set and specify many different types of data in the characteristics. You can decide what field type works best for your Configuration and Template needs.

What characteristics are available on a record are defined by the record's template

```json
"template": {
    "templateId": 1,
    "templateName": "Template Name",
    "processId": 0,
    "processName": null
}
```

A template will then define all the characteristics including each of the fields' data type.\
Here is an example of template from the API

```json
{
     "fields": [
        {
           "fieldName": "Field Name",
           "label": "field_label",
           "required": false,
           "maxLength": 500,
           "editable": false,
           "dataType": "AlphaNumericText",
           "allowMultiple": false,
           "listOfValues": []
        },
        ...
    ]
}       
```
