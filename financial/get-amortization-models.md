# Get amortization models

## Retrieve amortization models list

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/amortization/list`

This endpoint allows you to retrieve a list of all amortization models.

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Amortization models retrieved successfully." %}
```javascript
[
    {
        "id": 12,
        "name": "12 Month Curve",
        "periods": [
            {
                "id": 205,
                "lastUpdatedDate": "2019-07-18T06:15:58.410Z",
                "split": 20.0
            },
            {
                "id": 206,
                "lastUpdatedDate": "2019-07-18T06:15:58.420Z",
                "split": 15.0
            },
            {
                "id": 207,
                "lastUpdatedDate": "2019-07-18T06:15:58.427Z",
                "split": 15.0
            },
            {
                "id": 208,
                "lastUpdatedDate": "2019-07-18T06:15:58.430Z",
                "split": 10.0
            },
            {
                "id": 209,
                "lastUpdatedDate": "2019-07-18T06:15:58.437Z",
                "split": 5.0
            },
            {
                "id": 210,
                "lastUpdatedDate": "2019-07-18T06:15:58.437Z",
                "split": 5.0
            },
            {
                "id": 211,
                "lastUpdatedDate": "2019-07-18T06:15:58.443Z",
                "split": 5.0
            },
            {
                "id": 212,
                "lastUpdatedDate": "2019-07-18T06:15:58.447Z",
                "split": 5.0
            },
            {
                "id": 213,
                "lastUpdatedDate": "2019-07-18T06:15:58.450Z",
                "split": 5.0
            },
            {
                "id": 214,
                "lastUpdatedDate": "2019-07-18T06:15:58.457Z",
                "split": 5.0
            },
            {
                "id": 215,
                "lastUpdatedDate": "2019-07-18T06:15:58.463Z",
                "split": 5.0
            },
            {
                "id": 216,
                "lastUpdatedDate": "2019-07-18T06:15:58.467Z",
                "split": 5.0
            }
        ]
    },
    {
        "id": 77,
        "name": "4 Month Curve",
        "periods": [
            {
                "id": 2638,
                "lastUpdatedDate": "2020-12-02T18:17:28.380Z",
                "split": 60.0
            },
            {
                "id": 2639,
                "lastUpdatedDate": "2020-12-02T18:17:28.380Z",
                "split": 20.0
            },
            {
                "id": 2640,
                "lastUpdatedDate": "2020-12-02T18:17:28.380Z",
                "split": 15.0
            },
            {
                "id": 2641,
                "lastUpdatedDate": "2020-12-02T18:17:28.397Z",
                "split": 5.0
            }
        ]
    }
]
```
{% endtab %}
{% endtabs %}

## Retrieve amortization model

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/amortization/model/:modelID`

This endpoint allows you to retrieve an amortization model by ID.

#### Path Parameters

| Name                                      | Type   | Description            |
| ----------------------------------------- | ------ | ---------------------- |
| modelID<mark style="color:red;">\*</mark> | number | Amortization model ID. |

#### Headers

| Name                                             | Type   | Description             |
| ------------------------------------------------ | ------ | ----------------------- |
| x-api-key<mark style="color:red;">\*</mark>      | string | Your company's API key. |
| Authentication<mark style="color:red;">\*</mark> | string | Authentication token.   |

{% tabs %}
{% tab title="200 Amortization model retrieved successfully." %}
```javascript
{
    "id": 12,
    "name": "12 Month Curve",
    "periods": [
        {
            "id": 205,
            "split": 20.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.410Z"
        },
        {
            "id": 206,
            "split": 15.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.420Z"
        },
        {
            "id": 207,
            "split": 15.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.427Z"
        },
        {
            "id": 208,
            "split": 10.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.430Z"
        },
        {
            "id": 209,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.437Z"
        },
        {
            "id": 210,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.437Z"
        },
        {
            "id": 211,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.443Z"
        },
        {
            "id": 212,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.447Z"
        },
        {
            "id": 213,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.450Z"
        },
        {
            "id": 214,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.457Z"
        },
        {
            "id": 215,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.463Z"
        },
        {
            "id": 216,
            "split": 5.000000000,
            "lastUpdatedDate": "2019-07-18T06:15:58.467Z"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
