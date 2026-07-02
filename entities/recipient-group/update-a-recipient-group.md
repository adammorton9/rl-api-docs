# Update a Recipient Group

`PUT` `https://ris.rightsline.com/v4/recipient-group/:id`

**Path Parameters**

| Name | Type    | Description                                     |
| ---- | ------- | ----------------------------------------------- |
| id\* | integer | The unique ID of the recipient group to update. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Request Body**

| Name               | Type    | Description                                                     |
| ------------------ | ------- | --------------------------------------------------------------- |
| templateId\*       | integer | The unique ID of the template assigned to this recipient group. |
| characteristics    | object  | Key-value pairs of field tag labels and their values.           |
| parentRelationship | array   | Optional parent entity associations.                            |

**Response**

Returns the updated recipient group object. See [Retrieve a Recipient Group](https://file+.vscode-resource.vscode-cdn.net/c%3A/Users/JeffLinton/Downloads/recipient-group-api-docs.md#retrieve-a-recipient-group) for the response shape.
