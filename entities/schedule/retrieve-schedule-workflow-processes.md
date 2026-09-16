# Retrieve schedule workflow processes

## Get schedule workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/schedule-processes`

This endpoint allows you to retrieve workflow processes for schedules.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Schedule processes retrieved successfully." %}
```json
{
    "processes": [
        {
            "processId": 1,
            "processName": "Schedule Workflow",
            "sequenceNumber": 1,
            "description": "Schedule Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
