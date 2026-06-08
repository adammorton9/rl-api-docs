# Delete SSO configuration



## Delete SSO configuration

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/sso/:id`

This endpoint allows you to get sso configuration(s).

#### Query Parameters

| Name                               | Type   | Description              |
| ---------------------------------- | ------ | ------------------------ |
| <mark style="color:red;">\*</mark> | number | The Url Type Id (4,3,1). |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 SSO configuration is removed" %}
```
true
```
{% endtab %}

{% tab title="401: Unauthorized Invalid permissions to access the endpoint" %}

{% endtab %}
{% endtabs %}
