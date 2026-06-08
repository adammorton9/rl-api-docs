# Retrieve project workflow processes

## Get project workflow processes

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/project-processes`

This endpoint allows you to retrieve workflow processes for projects.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Project processes retrieved successfully." %}
```javascript
{
    "processes": [
        {
            "processId": 9,
            "processName": "Submission Out Workflow",
            "sequenceNumber": 1,
            "description": "Submission Out Workflow Description"
        },
        {
            "processId": 11,
            "processName": "Submission In Workflow",
            "sequenceNumber": 2,
            "description": "Submission In Workflow Description"
        },
        {
            "processId": 24,
            "processName": "Project Workflow",
            "sequenceNumber": 3,
            "description": "Project Workflow Description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

