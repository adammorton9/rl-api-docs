# Update a contract scope

`PUT` `https://ris.rightsline.com/v4/contract-scope/:id`

**Path Parameters**

| Name | Type    | Description                                    |
| ---- | ------- | ---------------------------------------------- |
| id\* | integer | The unique ID of the contract scope to update. |

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Request Body**

| Name               | Type    | Description                                                    |
| ------------------ | ------- | -------------------------------------------------------------- |
| templateId\*       | integer | The unique ID of the template assigned to this contract scope. |
| characteristics    | object  | Key-value pairs of field tag labels and their values.          |
| parentRelationship | array   | Optional parent entity associations.                           |

**Response**

Returns the updated contract scope object. See [Retrieve a contract scope](https://file+.vscode-resource.vscode-cdn.net/c%3A/Users/JeffLinton/repos/rightsline/Services/RightsLine.RestApi/Tests/contract-scope-api-docs.md#retrieve-a-contract-scope) for the response shape.
