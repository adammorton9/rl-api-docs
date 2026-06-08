# Execute relative rights profile

## Execute relative rights profile

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/relative-rights-profile`

This endpoint allows you to execute a relative rights profile.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

#### Request Body

| Name                                         | Type   | Description                        |
| -------------------------------------------- | ------ | ---------------------------------- |
| id<mark style="color:red;">\*</mark>         | int    | ID of the relative rights profile. |
| dealId<mark style="color:red;">\*</mark>     | int    | Deal ID.                           |
| catalogIds<mark style="color:red;">\*</mark> | int\[] | Array of catalog item IDs.         |

{% tabs %}
{% tab title="200 Relative rights executed successfully.  Use the GET /batch endpoint to retrieve the new records." %}
```json
{
    "batchId": 12000,
    "batchStatus": "Created"
}
```
{% endtab %}
{% endtabs %}
