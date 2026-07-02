# Switch contract scope template

`POST` `https://ris.rightsline.com/v4/contract-scope/:id/switch-template`

**Path Parameters**

| Name | Type    | Description                          |
| ---- | ------- | ------------------------------------ |
| id\* | integer | The unique ID of the contract scope. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Request Body**

| Name            | Type    | Description                          |
| --------------- | ------- | ------------------------------------ |
| id\*            | integer | The unique ID of the contract scope. |
| newTemplateId\* | integer | The ID of the template to switch to. |

**Response**

```
{
  "id": 1,
  "relationshipsNotMigrated": { "parties": [], "associations": {} },
  "characteristicsNotMigrated": [],
  "characteristicsRequiredOnNewTemplate": []
}
```
