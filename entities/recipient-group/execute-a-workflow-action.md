# Execute a Workflow Action

`PUT` `https://ris.rightsline.com/v4/recipient-group/:id/execute-workflow-action/:actionId`

**Path Parameters**

| Name       | Type    | Description                                      |
| ---------- | ------- | ------------------------------------------------ |
| id\*       | integer | The unique ID of the recipient group.            |
| actionId\* | integer | The unique ID of the workflow action to execute. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Response**

```
"Workflow Action Executed Successfully"
```
