# Apply user applications

## Apply user applications

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/user/:userID/app`

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name                                     | Type   | Description                                                                                                                  |
| ---------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------- |
| appIds<mark style="color:red;">\*</mark> | int\[] | An array of application IDs to grant access.  Any existing applications not included in array will have permissions removed. |

{% tabs %}
{% tab title="200: OK User applications applied." %}
```json
{
    "message": "User applications applied."
}
```
{% endtab %}
{% endtabs %}
