# Associate royalty set to catalog

## Associate royalty set to catalog

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/relationship`

This endpoint allows you to create a new relationship between the royalty set deal relationship and a catalog item.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                               | Type   | Description                                         |
| -------------------------------------------------- | ------ | --------------------------------------------------- |
| parentRecordId<mark style="color:red;">\*</mark>   | number | The ID of the parent royalty set deal relationship. |
| parentCharTypeId<mark style="color:red;">\*</mark> | number | 0                                                   |
| childRecordId<mark style="color:red;">\*</mark>    | number | The ID of the child catalog item.                   |
| childCharTypeId<mark style="color:red;">\*</mark>  | number | 1                                                   |

{% tabs %}
{% tab title="200 Relationship created successfully." %}
```
455
```
{% endtab %}
{% endtabs %}

### Sample Request

```javascript
{
    "parentCharTypeId": 0,
    "parentRecordId": 156848886,
    "childCharTypeId": 1,
    "childRecordId": 222
}
```
