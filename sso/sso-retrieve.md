# Retrieve SSO configuration



## Get SSO configuration

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/sso/:id`

This endpoint allows you to get sso configuration(s).

#### Query Parameters

| Name                               | Type   | Description                                                                                                                                 |
| ---------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:red;">\*</mark> | number | The Url Type Id (4,3,1). Required to be there but if either 4,3, or 1 is not provided the endpoint returns all sso configuration for the di |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 SSO configuration is returned" %}
```
[
    {
        "x509Certificate": "...",
        "ssoAuthXml": "...",
        "identityProvider": "identity-endpoint.com",
        "urlTypeId": 4,
        "url": "https://beta-dev.rightsline.com/"
    }
]
```
{% endtab %}

{% tab title="401: Unauthorized Invalid permissions to access the endpoint" %}

{% endtab %}
{% endtabs %}
