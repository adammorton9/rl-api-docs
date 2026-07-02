# Retrieve a Recipient Group

`GET` `https://ris.rightsline.com/v4/recipient-group/:id`

**Path Parameters**

| Name | Type    | Description                           |
| ---- | ------- | ------------------------------------- |
| id\* | integer | The unique ID of the recipient group. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Query Parameters**

| Name         | Type    | Description                                                                     |
| ------------ | ------- | ------------------------------------------------------------------------------- |
| extendedData | boolean | When `true`, returns additional field metadata alongside characteristic values. |

**Response**

```
{
  "id": 1,
  "title": "Recipient Group Title",
  "template": {
    "templateId": 1,
    "templateName": "Default",
    "processId": 0,
    "processName": null
  },
  "status": {
    "statusId": 1,
    "statusName": "Created"
  },
  "characteristics": {},
  "createdById": 1,
  "createdDate": "2024-01-01T00:00:00.000Z",
  "lastUpdatedById": 1,
  "lastUpdatedDate": "2024-01-01T00:00:00.000Z"
}
```
