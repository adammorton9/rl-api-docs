---
description: Limits on the number of API requests for a given time period.
---

# API request limits

Requests to the Rightsline API are limited on a per-second and per-day basis.

Calls to the Rightsline API v4 are limited as follows:

* Your application can make no more than 40 requests per second
* Your application can make up to 500,000 signed requests per day (dependent on user license count)

If a request is made beyond the limits described above, the API will respond with a status code of **429: Too Many Requests**. If you receive this response, you can wait a few seconds and try the request again.  If you receive another 429 response, this is most likely due to you exceeding your daily request limit.

If you believe you have exceeded your daily API request limit, you can contact your Rightsline representative to confirm.  Rightsline may be able to provide suggestions on how to consolidate the requests that you are making.

To programmatically check both the daily request maximum as well as how many are remaining in a given 24 hour period, use the `/limits` endpoint as follow:&#x20;

## Get request limits

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/limits`

This endpoint will return the maximum allowed requests for a 24 hour period as well as how many are remaining in the current day. Additionally, it will return the number of concurrent [Batch ](../batch/create.md)requests allowed and how many are remaining.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | String | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | String | Authentication token.   |

{% tabs %}
{% tab title="200: OK Successfully return request limits" %}
```json
{
    "dailyApiRequests": {
        "max": 500000,
        "remaining": 499987
    },
    "concurrentProcessingApiBatches": {
        "max": 10,
        "remaining": 10
    },
    "maxApiRequestsPerSecond": 20
}
```
{% endtab %}
{% endtabs %}
