# Get unavailable reasons

## Get reason unavailable list

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/avails/dimension-data`

Retrieve the list of possible unavailable reasons for Rights Actions.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Returns unavailable reasons." %}
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
