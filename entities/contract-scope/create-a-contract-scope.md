# Create a contract scope

`POST` `https://ris.rightsline.com/v4/contract-scope`

**Header**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Request Body**

| Name                  | Type    | Description                                                     |
| --------------------- | ------- | --------------------------------------------------------------- |
| template.templateId\* | integer | The unique ID of the template to assign to this contract scope. |
| characteristics       | object  | Key-value pairs of field tag labels and their values.           |
| parentRelationship    | array   | Optional parent entity associations.                            |

**Response**

```
14462
```
