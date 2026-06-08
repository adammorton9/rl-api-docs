# Create a data default

## Create a data default set

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/:charType/data-default`

Create a new data default for a char type.

#### Path Parameters

| Name                                       | Type   | Description                                                               |
| ------------------------------------------ | ------ | ------------------------------------------------------------------------- |
| charType<mark style="color:red;">\*</mark> | string | Char Type that data default set will apply to. (deal, catalog-item, etc.) |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                            | Type   | Description                                                                        |
| ----------------------------------------------- | ------ | ---------------------------------------------------------------------------------- |
| recordIds<mark style="color:red;">\*</mark>     | ids    | List of records that the set contains. This will be the table or right record ids. |
| label<mark style="color:red;">\*</mark>         | string | Name of the list, will show in UI.                                                 |
| setCharTypeId<mark style="color:red;">\*</mark> | id     | Char Type Id that the recordIds are.                                               |

{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    "id": "0f5ea7c5-e469-ed11-8340-065151be1e5f",
    "label": "Test From API"
}
```
{% endtab %}

{% tab title="400: Bad Request No data default "label"" %}
```javascript
{
    "message": "A valid label must be supplied for the data default."
}
```
{% endtab %}

{% tab title="400: Bad Request No recordIds" %}
```javascript
{
    "message": "At lesat one record id is required in 'recordids'."
}
```
{% endtab %}

{% tab title="400: Bad Request setCharTypeId is not one of the acceptable types (3 or 5)" %}
```javascript
{
    "message": "Valid char type for the data default records must be supplied."
}
```
{% endtab %}
{% endtabs %}

### Sample Create Data Default Request Body - 2 Table rows, for a table profile

```javascript
{
    "recordIds": [
        2485974,
        2485975
    ],
    "setCharTypeId": 5,
    "label": "Test From API"
}
```
