# Retrieve Recipient Group Validation Errors

`GET` `https://ris.rightsline.com/v4/recipient-group/:id/validation-errors`

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

```
{
  "hasErrors": false,
  "errors": [],
  "message": "No validation errors exist."
}
```
