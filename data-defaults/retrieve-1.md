# Delete data default

## Delete a Data Default

<mark style="color:red;">`DELETE`</mark> `https://ris.rightsline.com/v4/:charType/data-default/:dataDefaultGuid`

This endpoint deletes a single specified data default.

#### Path Parameters

| Name                                              | Type | Description                   |
| ------------------------------------------------- | ---- | ----------------------------- |
| dataDefaultGuid<mark style="color:red;">\*</mark> | GUID | Data default GUID to destroy. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Successfully deleted." %}
```javascript
 "Deleted"
```
{% endtab %}

{% tab title="400: Bad Request Failed to provide data default GUID." %}
```javascript
{
    // Response
}
```
{% endtab %}
{% endtabs %}

## Sample Url for Deal Data Defaultode

```
DELETE: /v4/deal/data-default/03a97200-e269-ed11-8340-065151be1e5
```

