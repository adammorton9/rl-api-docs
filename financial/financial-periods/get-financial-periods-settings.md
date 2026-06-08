# Get financial periods settings

## Retrieve financial periods settings

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/financial-periods-settings`

This endpoint retrieves an array of all financial periods settings, the available process for amounts as well as the Action associated with each process.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Financial Periods settings successfully retrieved." %}
```javascript
[
    {
        "processName": "Amount Workflow",
        "processId": 8,
        "actionId": 8,
        "actionName": "Deactivate, Make Not Deletable, Lock"
    },
    {
        "processName": "Locked Amounts Post-release",
        "processId": 38,
        "actionId": 2,
        "actionName": "Go to the Locked Status"
    },
    {
        "processName": "Advance Payment Workflow",
        "processId": 64,
        "actionId": null,
        "actionName": null
    },
    {
        "processName": "Sub-Allocation Workflow",
        "processId": 77,
        "actionId": null,
        "actionName": null
    }
]
```
{% endtab %}
{% endtabs %}
