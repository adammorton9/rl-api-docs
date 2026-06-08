# Get roles

## Get user roles

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/user/role`

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK User roles retrieved successfully." %}
```json
{
    "identityRoles": [
        {
            "id": "f2f5ecb8-b2db-4690-866d-9abbe6a97a54",
            "name": "Admin",
            "xref": "test4"
        },
        {
            "id": "799b1ace-27ee-4c75-9568-685fc8eeadc0",
            "name": "Default Role for External User "
        },
        {
            "id": "8c557f75-62c0-47c5-88a7-ea0f14ff2c92",
            "name": "Default Role for Internal User "
        },
        {
            "id": "3d4e462b-20aa-4b62-91cb-1b9cf97bdc21",
            "name": "Default Role for Rest API ",
            "xref": "role-xref1"
        },
        {
            "id": "469a0ede-dca5-4b68-a5ef-43a8dfe9f5cf",
            "name": "Full Admin",
            "xref": "another_xref"
        }
    ],
    "workflowRoles": [
        {
            "id": 1,
            "name": "Super Admin"
        },
        {
            "id": 2,
            "name": "Admin User"
        },
        {
            "id": 3,
            "name": "Full User"
        },
        {
            "id": 4,
            "name": "External User"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
