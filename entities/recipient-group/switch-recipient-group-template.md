# Switch Recipient Group Template

`POST` `https://ris.rightsline.com/v4/recipient-group/:id/switch-template`

**Path Parameters**

| Name | Type    | Description                           |
| ---- | ------- | ------------------------------------- |
| id\* | integer | The unique ID of the recipient group. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Request Body**

| Name            | Type    | Description                           |
| --------------- | ------- | ------------------------------------- |
| id\*            | integer | The unique ID of the recipient group. |
| newTemplateId\* | integer | The ID of the template to switch to.  |

**Response**

```
{
  "id": 1,
  "relationshipsNotMigrated": { "parties": [], "associations": {} },
  "characteristicsNotMigrated": [],
  "characteristicsRequiredOnNewTemplate": []
}
```
