# Update user messaging

## Update user messaging

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/user/:userID/messaging`

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name            | Type    | Description                                                                                                                                  |
| --------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| disableMessages | boolean | If true, activity from this user will not generate audit messages.  If false or not included in request, audit messages will send as normal. |

{% tabs %}
{% tab title="200: OK User messaging updated." %}
```javascript
{
    "message": "User messaging settings updated."
}
```
{% endtab %}
{% endtabs %}
