# Retrieve copy warnings

`GET` `https://ris.rightsline.com/v4/contract-scope/:id/copy-warnings`

**Path Parameters**

| Name | Type    | Description                          |
| ---- | ------- | ------------------------------------ |
| id\* | integer | The unique ID of the contract scope. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Query Parameters**

| Name         | Type    | Description                          |
| ------------ | ------- | ------------------------------------ |
| templateId\* | integer | The template ID to use for the copy. |
