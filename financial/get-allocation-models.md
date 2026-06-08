# Get allocation models

## Retrieve allocation models list

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/allocation-model-list`

This endpoint allows you to retrieve a list of all allocation models.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Allocation models successfully retrieved." %}
```javascript
[
    {
        "id": "fb615348-876b-ee11-834a-024eb66dbf05",
        "name": "Allocation 1",
        "parentCharTemplateID": 2
    },
    {
        "id": "a6cb6bec-146e-ee11-834b-065151be1e5f",
        "name": "Allocation 2",
        "parentCharTemplateID": 17
    },
    {
        "id": "20d3f6f3-8c70-ee11-834b-065151be1e5f",
        "name": "Allocation 3",
        "parentCharTemplateID": 45
    },
    {
        "id": "23d3f6f3-8c70-ee11-834b-065151be1e5f",
        "name": "Allocation 4",
        "parentCharTemplateID": 45
    }
]
```
{% endtab %}
{% endtabs %}
