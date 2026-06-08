# Retrieve data defaults

## Retrieve data default list

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/:charType/:id/data-default`

This endpoint allows you to retrieve a list of applicable data defaults.

#### Path Parameters

| Name                                       | Type   | Description                                         |
| ------------------------------------------ | ------ | --------------------------------------------------- |
| charType<mark style="color:red;">\*</mark> | string | Char type that the data defaults belong to.         |
| <mark style="color:red;">\*</mark>         | number | Record id that the data defaults are applicable to. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Batch successfully retrieved." %}
```javascript
[
    {
        "id": "297cc3df-33ad-e611-9457-0af1f058195a",
        "label": "test test",
        "charTypeId": 3,
        "templateIds": [
            2
        ]
    },
    {
        "id": "78bed71c-34ad-e611-9457-0af1f058195a",
        "label": "test rights profile",
        "charTypeId": 3,
        "templateIds": [
            1
        ]
    },
    {
        "id": "e16f610f-cf1f-e711-945b-0af1f058195a",
        "label": "test 1",
        "charTypeId": 3,
        "templateIds": [
            1
        ]
    }
]
```
{% endtab %}
{% endtabs %}

## Sample Url for Deal Data Default

```
/v4/deal/4576/data-default
```
