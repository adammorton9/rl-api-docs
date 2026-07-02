# Retrieve contract scope validation errors

`GET` `https://ris.rightsline.com/v4/contract-scope/:id/validation-errors`

**Path Parameters**

| Name | Type    | Description                          |
| ---- | ------- | ------------------------------------ |
| id\* | integer | The unique ID of the contract scope. |

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
