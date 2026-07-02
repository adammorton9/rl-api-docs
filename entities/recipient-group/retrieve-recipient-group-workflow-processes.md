# Retrieve Recipient Group Workflow Processes

`GET` `https://ris.rightsline.com/v4/recipient-group-processes`

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Response**

```
{
  "processes": [
    {
      "processId": 1,
      "processName": "Recipient Group Workflow",
      "sequenceNumber": 1,
      "description": ""
    }
  ]
}
```
