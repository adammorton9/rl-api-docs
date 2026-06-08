# Get user

## Get user

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/user/:userID`

#### Path Parameters

| Name                                     | Type | Description  |
| ---------------------------------------- | ---- | ------------ |
| userID<mark style="color:red;">\*</mark> | int  | The user ID. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK User retrieved successfully." %}
```json
{
    "email": "email@email.com",
    "characteristics":{
        "last_name": "Last",
        "email":"email@email.com",
        "first_name": "First"
    },
    "template":{
        "templateId": 3,
        "templateName": "User"
    },
    "appIds":[22,46],
    "workflowRoleIds":[2],
    "identityRoleIds":["895ba04a-7f03-4e3f-b659-f52e3066471a"],
    "disableMessages": true,
    "userLastActiveSession": "2026-04-01T20:00:30.359Z"
}
```
{% endtab %}
{% endtabs %}
