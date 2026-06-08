# Searching for deleted entities or relationships

While not as full featured as the search endpoints described in the rest of this section, the /search-deleted endpoints allow for some basic querying of both entities and relationships that have been deleted.

### The deleted entity search object

```javascript
{
  "startDate": "string",
  "endDate": "string",
  "deletedById": 0,
  "charType": 0,
  "recordId": 0,
  "templateId": 0,
  "statusId": 0,
  "createdStartDate": "string",
  "createdEndDate": "string",
  "createdById": 0,
  "updatedStartDate": "string",
  "updatedEndDate": "string",
  "updatedById": 0,
  "statusUpdateStartDate": "string",
  "statusUpdateEndDate": "string",
  "statusUpdateById": 0,
}
```

## Search For Deleted Entities

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/:entityType/search-deleted`

Search for an entity that has been deleted based on high level details and/or audit information. The start and end date of the audit window in which the delete occurred are the only required parameters and are limited to a 30 window to keep response sizes down.

#### Request Body

| Name                                        | Type   | Description                                                                                                                             |
| ------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| startDate<mark style="color:red;">\*</mark> | Date   | Beginning of the timeframe in which the delete occurred. ISO date format for the string. UTC time zone.                                 |
| endDate<mark style="color:red;">\*</mark>   | Date   | End of the timeframe in which the delete occurred. ISO date format for the string. UTC time zone. Limited to 30 days after `startDate.` |
| deletedById                                 | Number | ID of the user that performed the delete.                                                                                               |
| charType                                    | Number | ID for the type of entity deleted.                                                                                                      |
| recordId                                    | Number | ID of the entity deleted.                                                                                                               |
| templateId                                  | Number | Template ID of the entity deleted.                                                                                                      |
| statusId                                    | Number | Status ID of the entity deleted.                                                                                                        |
| createdStartDate                            | Date   | Beginning of the timeframe in which the entity was created. ISO date format for the string. UTC time zone.                              |
| createdEndDate                              | Date   | End of the timeframe in which the entity was created. ISO date format for the string. UTC time zone.                                    |
| createdById                                 | Number | ID of the user that created the entity.                                                                                                 |
| updatedStartDate                            | Date   | Beginning of the timeframe in which the entity was last updated. ISO date format for the string. UTC time zone.                         |
| updatedEndDate                              | Date   | End of the timeframe in which the entity was last updated. ISO date format for the string. UTC time zone.                               |
| updatedById                                 | Number | ID of the user that last updated the entity.                                                                                            |
| statusUpdatedStartDate                      | Date   | Beginning of the timeframe in which the entity's status was last updated. ISO date format for the string. UTC time zone.                |
| statusUpdatedEndDate                        | Date   | End of the timeframe in which the entity's status was last updated. ISO date format for the string. UTC time zone.                      |
| statusUpdatedById                           | Number | ID of the user that last updated the status of the entity.                                                                              |

{% tabs %}
{% tab title="200: OK Array of entities matching the filter criteria provided" %}
```json
[
    {
        "deletedById": 123456,
        "deletedDate": "2022-11-11T11:11:11.111Z",
        "id": 0,
        "revisionId": 0,
        "title": "111",
        "template": {
            "templateId": 0,
            "templateName": null,
            "processId": 0,
            "processName": null
        },
        "status": {
            "statusId": 0,
            "statusName": null
        },
        "characteristics": {},
        "comments": null,
        "createdById": 123456,
        "createdDate": "2022-01-11T00:00:00.000Z",
        "lastUpdatedById": 123456,
        "lastUpdatedDate": "2022-11-11T00:00:00.000Z",
        "statusUpdatedById": 123456,
        "statusUpdatedDate": "2022-10-10T00:00:00.000Z"
    }
]
```
{% endtab %}
{% endtabs %}

### The deleted relationship search object

```javascript
{
  "startDate": "string",
  "endDate": "string",
  "deletedById": 0,
  "parentCharType": 0,
  "parentRecordId": 0,
  "childCharType": 0,
  "childRecordId": 0,
  "createdStartDate": "string",
  "createdEndDate": "string",
  "createdById": 0
}
```

## Search for Deleted Relationships

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/relationship/search-deleted`

Search for a relationship that has been deleted based on high level details and/or audit information. The start and end date of the audit window in which the delete occurred are the only required parameters and are limited to a 30 window to keep response sizes down.

#### Request Body

| Name                                        | Type   | Description                                                                                                                             |
| ------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| startDate<mark style="color:red;">\*</mark> | Date   | Beginning of the timeframe in which the delete occurred. ISO date format for the string. UTC time zone.                                 |
| endDate<mark style="color:red;">\*</mark>   | Date   | End of the timeframe in which the delete occurred. ISO date format for the string. UTC time zone. Limited to 30 days after `startDate.` |
| deletedById                                 | Number | ID of the user that performed the delete.                                                                                               |
| createdStartDate                            | Date   | Beginning of the timeframe in which the relationship was created. ISO date format for the string. UTC time zone.                        |
| createdEndDate                              | Date   | End of the timeframe in which the relationship was created. ISO date format for the string. UTC time zone.                              |
| createdById                                 | Number | ID of the user that created the relationship.                                                                                           |

{% tabs %}
{% tab title="200: OK Array of relationships matching the filter criteria." %}
```javascript
[
    {
        "deletedById": 123456,
        "deletedDate": "2022-11-11T11:11:11.111Z",
        "id": 11111111,
        "relationshipType": {
            "relationshipTypeId": 0,
            "relationshipTypeName": "Default"
        },
        "createdById": 123456,
        "createdDate": "2022-01-01T01:01:01Z",
        "lastUpdatedById": 1784495,
        "lastUpdatedDate": "2022-02-02T02:02:02Z",
        "parentCharTypeId": 4,
        "parentRecordId": 4444,
        "childCharTypeId": 5,
        "childRecordId": 5555,
        "sequenceNumber": 0
    }
]
```
{% endtab %}
{% endtabs %}
