# Retrieve Recipient Group Date Alerts

`GET` `https://ris.rightsline.com/v4/recipient-group/:id/date-alerts`

**Path Parameters**

| Name | Type    | Description                           |
| ---- | ------- | ------------------------------------- |
| id\* | integer | The unique ID of the recipient group. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Response**

Returns an array of date alert objects. Returns `[]` when no alerts exist.

```
[
  {
    "id": 1,
    "tagLabel": "expiration_date",
    "charId": 100,
    "deliveryDate": "2024-12-31T00:00:00.000Z",
    "subject": "Alert: Expiration Date",
    "recipients": []
  }
]
```
