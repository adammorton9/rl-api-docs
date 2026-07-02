# Retrieve Copy Warnings

`GET` `https://ris.rightsline.com/v4/recipient-group/:id/copy-warnings`

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

| Name         | Type    | Description                          |
| ------------ | ------- | ------------------------------------ |
| templateId\* | integer | The template ID to use for the copy. |
