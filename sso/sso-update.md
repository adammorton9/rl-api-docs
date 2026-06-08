# Update SSO configuration

## Update SSO configuration

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/sso/:id`

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

#### Request Body

| Name                                              | Type   | Description       |
| ------------------------------------------------- | ------ | ----------------- |
| x509Certificate<mark style="color:red;">\*</mark> | string | X509 Certificate  |
| ssoAuthXml                                        | string | SSO Auth Xml      |
| identityProvider                                  | string | Identity Provider |

{% tabs %}
{% tab title="200 SSO configuration is updated and set" %}
```
true
```
{% endtab %}

{% tab title="401: Unauthorized Invalid permissions to access the endpoint" %}

{% endtab %}
{% endtabs %}

### Sample Request

```jsonp
{
    "x509Certificate": "test",
    "ssoAuthXml": "test",
    "identityProvider": "test"
}
```
