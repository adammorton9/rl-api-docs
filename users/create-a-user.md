---
description: Create a user with Rightsline access.
---

# Create a user

## Create a user

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/user`

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name                                                  | Type    | Description                                                                                                                                  |
| ----------------------------------------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| email<mark style="color:red;">\*</mark>               | string  | User login email address.                                                                                                                    |
| characteristics<mark style="color:red;">\*</mark>     | object  | The characteristics of the user entity.                                                                                                      |
| template<mark style="color:red;">\*</mark>            | object  | The template for the user entity.                                                                                                            |
| template.templateId<mark style="color:red;">\*</mark> | int     | The template ID of the user entity.                                                                                                          |
| appIds<mark style="color:red;">\*</mark>              | int\[]  | An array of integers for which applications the user has access to. See [Get Applications](get-applications.md).                             |
| workflowRoleIds<mark style="color:red;">\*</mark>     | int\[]  | An array of integers for the workflow roles assigned to the user. See [Get Roles](get-roles.md).                                             |
| identityRoleIds<mark style="color:red;">\*</mark>     | Guid\[] | An array of Guids for the identity roles assigned to the user. See [Get Roles](get-roles.md).                                                |
| disableMessages                                       | boolean | If true, activity from this user will not generate audit messages.  If false or not included in request, audit messages will send as normal. |

{% tabs %}
{% tab title="200: OK User created.  Returns the user ID." %}
```javascript
549846
```
{% endtab %}
{% endtabs %}

{% code title="POST /v4/user" %}
```json
{
    "email": "someone@gmail.com",
    "characteristics":{
        "last_name": "Last",
        "email":"someone@gmail.com",
        "first_name": "First"
    },
    "template":{
        "templateId": 3
    },
    "appIds":[24,80],
    "workflowRoleIds":[2],
    "identityRoleIds":["469a0ede-dca5-4b68-a5ef-43a8dfe9f5cf"],
    "disableMessages": false
}
```
{% endcode %}
