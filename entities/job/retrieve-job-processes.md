# Retrieve job workflow processes

## Get job workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/job-processes`

This endpoint allows you to retrieve workflow processes for jobs.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Job processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 12,
            "processName": "Job Workflow",
            "sequenceNumber": 1,
            "description": "Job Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

