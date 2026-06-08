---
description: Request temporary credentials to be used to authenticate API requests.
---

# Requesting temporary credentials

In accordance with AWS security recommendations, Rightsline utilizes expiring credentials to authenticate requests to our API.  These temporary credentials are valid for **1 hour.**  After these credentials expire, you will need to request a new set of temporary credentials.  These temporary credentials will be used to compute the Authentication signature for all other requests to the API.

{% hint style="info" %}
**With the April 30, 2025 Production release, requests to this endpoint will be limited to 300 requests per minute for a given IP address. All subsequent requests to this endpoint for that minute will receive a 429: Too Many Requests response.**
{% endhint %}

To obtain temporary credentials, send a request to the following endpoint:

## Request Temporary Credentials

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/auth/temporary-credentials`

#### Headers

| Name         | Type   | Description             |
| ------------ | ------ | ----------------------- |
| Content-Type | string | application/json        |
| x-api-key    | string | Your company's API key. |

#### Request Body

| Name      | Type   | Description                 |
| --------- | ------ | --------------------------- |
| accessKey | string | Your user's API access key. |
| secretKey | string | Your user's API secret key. |

{% tabs %}
{% tab title="200 Credentials accepted." %}
```javascript
{
    "accessKey": "***********",
    "secretKey": "***************************",
    "sessionToken": "FQoDYXd//////====ONCXz6OZC6FIxoWO1CGxVkwnY6WT07ZdLgGkr5ZkRCnGpa5uiF5KKbgMMWyQjKIazeyarBvXleDQmJznO4tBKq3U709cY20lVkdzHwAJQ5HXWHVop6w6cRy8uyOFPZ9fPD79PJ0L9KUkSo9uIG8DUK7PRvs4eAtIQQFdW+j2eHx6sUlF====34098qojfaof",
    "expiration": "2018-01-01T00:00:01+00:00"
}
```
{% endtab %}

{% tab title="401 Invalid credentials." %}
```
```
{% endtab %}
{% endtabs %}

### Example Request

```javascript
{
    "accessKey":"*****************",
    "secretKey":"***********************"
}
```

{% hint style="info" %}
See [Getting Started](../getting-started/#obtaining-api-credentials) for instructions on obtaining your access and secret keys.&#x20;
{% endhint %}
