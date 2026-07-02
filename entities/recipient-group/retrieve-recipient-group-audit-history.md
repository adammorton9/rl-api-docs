# Retrieve Recipient Group Audit History

`GET` `https://ris.rightsline.com/v4/recipient-group/:id/audit-history`

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

| Name         | Type    | Description                                                           |
| ------------ | ------- | --------------------------------------------------------------------- |
| userId       | integer | Filter by the user who made the change.                               |
| page         | integer | Page number (default: 1).                                             |
| rows         | integer | Results per page (default: 10).                                       |
| startDate    | string  | Start of date range filter (ISO 8601).                                |
| endDate      | string  | End of date range filter (ISO 8601).                                  |
| showWorkflow | boolean | When `true`, includes workflow transition history (default: `false`). |
