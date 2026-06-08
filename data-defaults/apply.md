---
description: >-
  This endpoint returns a batch id, you will need to use the batch GET endpoint
  to see the full results of this function.
---

# Apply data default



## Apply a data default set

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/:charType/:id/data-default`

Apply an existing data default to an existing record.

#### Path Parameters

| Name                                       | Type   | Description                                                               |
| ------------------------------------------ | ------ | ------------------------------------------------------------------------- |
| charType<mark style="color:red;">\*</mark> | string | Char Type that data default set will apply to. (deal, catalog-item, etc.) |
|                                            | id     | Record id to apply data default to.                                       |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                 | Type    | Description                                                                                                                                                                |
| ------------------------------------ | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id<mark style="color:red;">\*</mark> | GUID    | Data default GUID.                                                                                                                                                         |
| copyTitles                           | boolean | Defaults to FALSE. If set to true will use the same titles as the original source records. If false, the new records will have new titles, usually based on the record id. |

{% tabs %}
{% tab title="200: OK Successfully create a batch request to apply a data default." %}
```javascript
{
    "batchId": 48865381,
    "batchStatus": "Created"
}
```
{% endtab %}

{% tab title="400: Bad Request No request body" %}
```javascript
{
    "message": "Please provide valid request object with data default id."
}
```
{% endtab %}

{% tab title="400: Bad Request No data default id provided" %}
```javascript
{
    "message": "Please provide valid data default id."
}
```
{% endtab %}
{% endtabs %}

### Sample Apply Data Default Request Body

```javascript
{
    "id": "0f5ea7c5-e469-ed11-8340-065151be1e5f",
    "copyTitles": true
}
```
