# Apply user roles

## Apply user roles

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/user/:userID/role`

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name                                              | Type    | Description                                                                                                 |
| ------------------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------- |
| workflowRoleIds<mark style="color:red;">\*</mark> | int\[]  | An array of workflow role IDs to apply.  Any existing workflow roles not included in array will be removed. |
| identityRoleIds<mark style="color:red;">\*</mark> | Guid\[] | An array of identity role IDs to apply.  Any existing identity roles not included in array will be removed. |

{% tabs %}
{% tab title="200: OK User roles applied." %}
```json
{
    "message": "Roles applied."
}
```
{% endtab %}
{% endtabs %}
