# Delete user

## Delete user

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/user/:userID`

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
{% tab title="204: No Content User deleted successfully." %}

{% endtab %}

{% tab title="403: Forbidden Permission denied." %}
```json
{
    "message": "Acls don't provide permission to delete user."
}
```
{% endtab %}
{% endtabs %}
