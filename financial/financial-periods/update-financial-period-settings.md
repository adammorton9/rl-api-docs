# Update financial period settings

## Update financial period settings

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/financial-periods-settings`

This endpoint updates a div's financial period settings.\
The endpoint will set each specified action to the related process.\
`null` can be specified for the Action Id, which will change nothing.\
`-1` can be specified for the Action Id which will remove the selection for the action.

#### Query Parameters

| Name                               | Type   | Description                |
| ---------------------------------- | ------ | -------------------------- |
| <mark style="color:red;">\*</mark> | number | Id of the financial period |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                        | Type   | Description                                                    |
| ------------------------------------------- | ------ | -------------------------------------------------------------- |
| processId<mark style="color:red;">\*</mark> | number | The process to update                                          |
| actionId                                    | number | <p>Action to set for the process.<br>-1, null, or actionId</p> |

{% tabs %}
{% tab title="200 Settings updated, returns new settings." %}
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

{% tab title="400: Bad Request Invalid process was specified" %}
```javascript
{
    "message": "Process id 123 is not a valid amount process. The process must have at least 1 available action."
}
```
{% endtab %}

{% tab title="400: Bad Request Nothing to update" %}
```javascript
{
    "message": "At least one setting must be updated."
}
```
{% endtab %}

{% tab title="400: Bad Request Invalid action was specified" %}
```json
{
    "message": "Action id (11) is not available for the specified process (32)."
}
```
{% endtab %}
{% endtabs %}

### Example Request Body

The `processName` and `actionName` fields are not respected in this request body, they are only there to illustrate what is being updated. Only the `processId` and `actionId` matter.

```json
[
    {
        "processName": "Amount Workflow", // <-- The two name fields are not required
        "processId": 8,                   //     and have no impact
        "actionId": 8,
        "actionName": "Deactivate, Make Not Deletable, Lock" // <-- Has no impact
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
        "actionId": -1,
        "actionName": "Action ID -1 will remove a selection"
    },
    {
        "processName": "Sub-Allocation Workflow",
        "processId": 77,
        "actionId": null,
        "actionName": null
    }
]
```
