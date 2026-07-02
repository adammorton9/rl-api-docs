# Check Recipient Group Template Switch

`POST` `https://ris.rightsline.com/v4/recipient-group/:id/switch-template-check`

Preview what will change before committing to a template switch.

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
  "relationshipsNotMigrated": { "parties": [], "associations": {} },
  "characteristicsNotMigrated": [],
  "characteristicsRequiredOnNewTemplate": []
}
```
