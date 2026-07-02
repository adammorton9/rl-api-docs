# Retrieve Recipient Group Audit History Detail

`GET` `https://ris.rightsline.com/v4/recipient-group/:id/audit-history-detail`

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

| Name            | Type    | Description                                          |
| --------------- | ------- | ---------------------------------------------------- |
| auditId\*       | integer | The audit record ID from the audit history response. |
| sequence\*      | integer | The sequence number from the audit history response. |
| operationId\*   | integer | The operation ID from the audit history response.    |
| isHeader\*      | boolean | Whether this is a header-level audit record.         |
| includeMessages | boolean | When `true`, includes message delivery information.  |
