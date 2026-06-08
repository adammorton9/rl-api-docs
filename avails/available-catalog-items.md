# Get available catalog items

## Get available catalog items

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/avails/available-catalog-items`

This endpoint returns the availability for the specified catalog-items for the given dimensions.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                   | Type    | Description                                                                      |
| -------------------------------------- | ------- | -------------------------------------------------------------------------------- |
| dim1<mark style="color:red;">\*</mark> | array   | Array of type `INTEGER` of desired dim1 values                                   |
| dim2<mark style="color:red;">\*</mark> | array   | Array of type `INTEGER` of desired dim2 values                                   |
| dim3<mark style="color:red;">\*</mark> | array   | Array of type `INTEGER` of desired dim3 values                                   |
| dim4<mark style="color:red;">\*</mark> | array   | Array of type `INTEGER` of desired dim4 values                                   |
| windowStart                            | string  | yyyy-mm-dd format                                                                |
| windowEnd                              | string  | yyyy-mm-dd format                                                                |
| matchType                              | string  | CoverEntire, OverlapPart, StartWithin, EndWithin                                 |
| isExact                                | boolean | True for if the window dates should match exactly, False for flexible            |
| isExclusive                            | boolean | True for Exclusive, False for Non-Exclusive, null for no value                   |
| start                                  | string  | Record count start (0-based index)                                               |
| rows                                   | integer | Page result count (25 recommended)                                               |
| characteristics                        | object  | Filter by specific LOV characteristic values on the catalog-item.                |
| templateIds                            | array   | Array of type `INTEGER` of template IDs to filter by                             |
| statusIds                              | array   | Array of type `INTEGER` of status IDs to filter by                               |
| rightTemplateIds                       | array   | Array of type `INTEGER` of template IDs of the associated rightsets to filter by |
| includeRecalcStatus                    | boolean | If true, a recalcStatus will be returned with the results. Defaults to false.    |

{% tabs %}
{% tab title="200 The availability for the requested catalog items." %}
```javascript
{
    "rowCount": 2,
    "rows": [
        {
            "id": 100,
            "status": {
                "statusId": 2,
                "statusName": "Packaging/Financing"
            },
            "template": {
                "processId": 0,
                "processName": null,
                "templateId": 1,
                "templateName": "Feature"
            },
            "title": "Title 1"
        },
        {
            "id": 101,
            "status": {
                "statusId": 1,
                "statusName": "Development"
            },
            "template": {
                "processId": 0,
                "processName": null,
                "templateId": 1,
                "templateName": "Feature"
            },
            "title": "Title 2"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

### Example API request body

```json
{
  "dim1": [6],
  "dim2": [43],
  "dim3": [29],
  "dim4": [], 
  "windowStart": "2021-10-01", 
  "windowEnd": "2021-10-31",   
  "isExclusive": false,
  "matchType": "CoverEntire",
  "isExact": false,
  "start": 0,   
  "rows": 25,
  "templateIds": [1,2],
  "statusIds": [1],
  "characteristics":{
      "genre":["Adventure"]
  },
  "rightTemplateIds":[2,4]
}
```

{% hint style="info" %}
The characteristics field allows you to filter the catalog items in the response that contain a specific value or group of values for a given characteristic.  In the example request above, only catalog items that have a genre value of Adventure will be returned in the response.
{% endhint %}

### Example API response

```json
{
    "rowCount": 2,
    "rows": [
        {
            "id": 100,
            "status": {
                "statusId": 2,
                "statusName": "Packaging/Financing"
            },
            "template": {
                "processId": 0,
                "processName": null,
                "templateId": 1,
                "templateName": "Feature"
            },
            "title": "Title 1"
        },
        {
            "id": 101,
            "status": {
                "statusId": 1,
                "statusName": "Development"
            },
            "template": {
                "processId": 0,
                "processName": null,
                "templateId": 1,
                "templateName": "Feature"
            },
            "title": "Title 2"
        }
    ]
}
```
