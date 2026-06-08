# Associate royalty split to royalty set

## Associate royalty split to royalty set

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/relationship`

This endpoint allows you to create a new relationship between a royalty split table and a royalty set deal relationship.

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
| childRecordId<mark style="color:red;">\*</mark>    | number | The ID of the child royalty split.                  |
| childCharTypeId<mark style="color:red;">\*</mark>  | number | 5                                                   |

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
    "parentRecordId": 215655,
    "childCharTypeId": 5,
    "childRecordId": 222
}
```
