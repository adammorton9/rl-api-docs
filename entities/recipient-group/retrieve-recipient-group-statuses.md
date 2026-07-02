# Retrieve Recipient Group Statuses

`GET` `https://ris.rightsline.com/v4/recipient-group-statuses/:templateId`

**Path Parameters**

| Name         | Type    | Description                      |
| ------------ | ------- | -------------------------------- |
| templateId\* | integer | The recipient group template ID. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Response**

```
{
  "statuses": [
    {
      "statusId": 1,
      "statusName": "Created"
    }
  ]
}
```
