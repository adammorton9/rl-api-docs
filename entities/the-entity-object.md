---
description: >-
  All Rightsline entities share a common structure.  This structure is used to
  enforce consistency across different entity types.
---

# The entity object

## Attributes

### ID $$int$$&#x20;

The unique identifier of the entity.  Each entity has an ID value that is unique to that specific record of that specific entity type.  ID values are not unique across different entity types.  This means that when referencing a particular entity, both entity type and ID are required.

```json
"id": 123
```

### Template $$object$$&#x20;

The details of any particular entity are defined by the template value of the entity.  A template defines the possible characteristics and relationships of an entity.  A template is composed of a template ID and a template name.&#x20;

```json
"template": {
    "templateId": 1,
    "templateName": "Feature",
    "processId": 0,
    "processName": "Catalog Process"
}
```

### Title $$string$$&#x20;

A descriptive title of the entity.

```json
"title": "This Movie Is Great!"
```

### Characteristics $$object$$

A collection of attributes that define specific details about an entity.  Characteristics are a set of key-value pairs, where the key is a unique-string identifier, and the value can be of any datatype including: date, integer, string, List-Of-Value option, array, currency, etc.

```json
"characteristics": {
    "territory": [
        {
            "id": 1,
            "value": "United States of America",
            "xref": "USA"
        }
    ],
    "start_date": "2024-01-01",
    "end_date": "2025-01-01"
}
```

### Characteristics Extended $$object$$ (optional)

A collection of attributes that define additional information about a given set of characteristics. Extended Characteristics are a set of key-value pairs, where the key is the unique-string identifier of the characteristic, and the value is an object with the properties: `"estimated"` and `"blockDateMath"`. This object is only returned when the query parameter `extendedData` is set to `true` in the request.

```json
"characteristicsExtended": {
    "start_date": {
        "estimated": true,
        "blockDateMath": true
    },
    "end_date": {
        "estimated": true,
        "blockDateMath": false
    }
}
```

## Entity object structure example

```javascript
{
  "parentRelationship": [
    {
      "id": 0,
      "parentTemplate": {
        "templateId": 0,
        "templateName": "string"
      },
      "parentStatus": {
        "statusId": 0,
        "statusName": "string"
      },
      "childTemplate": {
        "templateId": 0,
        "templateName": "string"
      },
      "childStatus": {
      "statusId": 0,
        "statusName": "string"
      },
      "relationshipType": {
        "relationshipTypeId": 0,
        "relationshipTypeName": "string"
      },
      "createdById": 0,
      "createdDate": "2020-06-04T19:39:02.584Z",
      "lastUpdatedById": 0,
      "lastUpdatedDate": "2020-06-04T19:39:02.584Z",
      "parentCharTypeId": 0,
      "parentRecordId": 0,
      "childCharTypeId": 0,
      "childRecordId": 0,
      "sequenceNumber": 0
    }
  ],
  "parentRelationshipCount": 0,
  "id": 0,
  "revisionId": 0,
  "title": "string",
  "template": {
    "fields": [
      {
        "fieldName": "string",
        "label": "string",
        "required": true,
        "maxLength": 0,
        "editable": true,
        "dataType": "string",
        "allowMultiple": true,
        "listOfValues": [
          {
            "id": 0,
            "label": "string",
            "xref": "string",
            "childValues": [
              {}
            ]
          }
        ]
      }
    ],
    "templateId": 0,
    "templateName": "string",
    "processId": 0,
    "processName": "string"
  },
  "status": {
    "statusId": 0,
    "statusName": "string"
  },
  "characteristics": {},
  "characteristicsExtended": {},
  "comments": [
    {
      "parentID": 0,
      "id": 0,
      "userID": 0,
      "userName": "string",
      "userEmail": "string",
      "profileAvatar": "string",
      "entityID": "string",
      "text": "string",
      "created": "2020-06-04T19:39:02.584Z",
      "updated": "2020-06-04T19:39:02.584Z",
      "children": [
        {}
      ]
    }
  ],
  "createdById": 0,
  "createdDate": "2020-06-04T19:39:02.584Z",
  "lastUpdatedById": 0,
  "lastUpdatedDate": "2020-06-04T19:39:02.584Z",
  "statusUpdatedById": 0,
  "statusUpdatedDate": "2020-06-04T19:39:02.584Z"
}
```
