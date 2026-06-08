# Calculate allocations

Sample Calculate Allocations request:

```json
{
    "rightsDimensionId": "1e7033ea-7430-11ee-b962-0242ac120002", // optional
    "catalogDistribution": "EVENLY",
    "hierarchyDistribution": "SELECTED_CATALOG",
    "rollupToOneAmount": false,
    "allocationRows":[
        {
            "catalogRecordId": 100,
            "paymentScheduleRecordId": 500,
            "allocatedAmount": 2000.01 // optional
        },
        {
            "catalogRecordId": 101,
            "paymentScheduleRecordId": 500,
            "allocatedAmount": 3999.99 // optional
        },
        {
            "catalogRecordId": 102,
            "paymentScheduleRecordId": 500,
            "allocatedAmount": 4000.00 // optional
        }
    ]
}
```

{% hint style="info" %}
Specifying an **allocatedAmount** for each allocation row will override the distribution type and will instead create amounts with the specified allocatedAmount value.
{% endhint %}

## Calculate allocations

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/deal/:dealID/calculate-allocations`

This endpoint allows you to calculate allocations.

#### Path Parameters

| Name                                     | Type | Description  |
| ---------------------------------------- | ---- | ------------ |
| dealID<mark style="color:red;">\*</mark> | int  | The deal ID. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name                                                    | Type             | Description                              |
| ------------------------------------------------------- | ---------------- | ---------------------------------------- |
| rightsDimensionId                                       | Guid             | The allocation model ID (optional).      |
| catalogDistribution<mark style="color:red;">\*</mark>   | String           | EVENLY or BY\_RIGHTS\_DURATION           |
| hierarchyDistribution<mark style="color:red;">\*</mark> | String           | SELECTED\_CATALOG or IMMEDIATE\_CHILDREN |
| rollupToOneAmount<mark style="color:red;">\*</mark>     | bool             | Roll up to one amount.                   |
| allocationRows<mark style="color:red;">\*</mark>        | AllocationRow\[] | List of allocation rows.                 |

{% tabs %}
{% tab title="202: Accepted Batch created successfully." %}
```javascript
{
    "batchId": 456840,
    "batchStatus": "Created"
}
```
{% endtab %}

{% tab title="409: Conflict Insufficient rights." %}
```json
{
    "message": "The selected model cannot be applied to these catalog items due to insufficient rights: [100,101]"
}
```
{% endtab %}

{% tab title="409: Conflict No Fee value." %}
```json
{
    "message": "Payment Schedule table does not have a Fee value."
}
```
{% endtab %}

{% tab title="409: Conflict Amounts do not add up to Fee." %}
```json
{
    "message": "The sum of the allocated amounts does not equal the Payment Schedule table 500 fee.."
}
```
{% endtab %}

{% tab title="409: Conflict Allocation template not configured for deal." %}
```json
{
    "message": "Configuration does not allow for Allocation tables to be created on deal {id}."
}
```
{% endtab %}

{% tab title="409: Conflict Sub-allocation template not configured on Allocation table." %}
```json
{
    "message": "Configuration does not allow for Sub-Allocation amounts to be created on Allocation tables."
}
```
{% endtab %}
{% endtabs %}
