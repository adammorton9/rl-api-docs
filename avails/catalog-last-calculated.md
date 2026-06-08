# Catalog last calculated

## Get catalog's calculation status

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/avails/recalc-status/{id}`

Get the timestamp of the last time the avails calculation ran for the catalog item with the matching id

#### Path Parameters

| Name | Type   | Description            |
| ---- | ------ | ---------------------- |
|      | String | relevant catalog item  |

{% tabs %}
{% tab title="200: OK " %}
```json
{
    "CalculationLastCompleted":"2023-11-11 12:00:00"
}
```
{% endtab %}
{% endtabs %}
