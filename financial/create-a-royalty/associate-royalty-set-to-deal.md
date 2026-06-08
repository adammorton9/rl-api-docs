# Associate royalty set to deal

## Associate royalty set to deal

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/relationship`

This endpoint allows you to create a new relationship between a deal and a royalty set.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                               | Type   | Description                      |
| -------------------------------------------------- | ------ | -------------------------------- |
| parentRecordId<mark style="color:red;">\*</mark>   | number | The ID of the parent deal.       |
| parentCharTypeId<mark style="color:red;">\*</mark> | number | 4                                |
| childRecordId<mark style="color:red;">\*</mark>    | number | The ID of the child royalty set. |
| childCharTypeId<mark style="color:red;">\*</mark>  | number | 13                               |

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
    "parentCharTypeId": 4,
    "parentRecordId": 111,
    "childCharTypeId": 13,
    "childRecordId": 222
}
```
