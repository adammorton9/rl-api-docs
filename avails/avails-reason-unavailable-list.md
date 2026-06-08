# Get reason unavailable list

## Get reason unavailable list

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/avails/reason-unavailable-list`

This endpoint returns availability dimension data.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Returns availability reasons unavailable." %}
```javascript
{
    "reasonUnavailable": [
        "NotWindowed",
        "LimitedByChildrenNoRightsIn",
        "LimitedByChildren",
        "LimitedByClearance",
        "NoRightsIn",
        "LimitedByOverrun",
        "InsufficientReapply",
        "RightsOutExist"
    ]
}
```
{% endtab %}
{% endtabs %}

