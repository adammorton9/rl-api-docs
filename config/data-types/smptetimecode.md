---
description: Configures an input field for a timecode
---

# SMPTETimeCode

Timecode is a time represented as Hours:Minutes:Seconds in the format of `hh:mm:ss`.

| Value Precision | is AllowMultiple respected? | Has validation? |
| --------------- | --------------------------- | --------------- |
| 00              | No                          | Yes             |

### SMPTETimeCode Data Type Definition

```json
{
     "fields" : [
     	{
	   "fieldName": "Time Code",
	   "label": "time_code",
	   "required": false,
	   "maxLength": 10000,
	   "editable": true,
	   "dataType": "SMPTETimeCode",
	   "allowMultiple": false,
	   "listOfValues": []
	},
        ...
    ]
}  
```
