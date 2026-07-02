# Retrieve contract scope statuses

`GET` `https://ris.rightsline.com/v4/contract-scope-statuses/:templateId`

**Path Parameters**

| Name         | Type    | Description                     |
| ------------ | ------- | ------------------------------- |
| templateId\* | integer | The contract scope template ID. |

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
