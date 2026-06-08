# Get availability

## Get availability request

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/avails/availability`

This endpoint returns the availability for the specified catalog-items for the given dimensions.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                                | Type    | Description                                                                                                                                                   |
| ----------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| recordId                            | array   | Array of type `INTEGER` of desired catalog items                                                                                                              |
| dim1                                | array   | Array of type `INTEGER` of desired dim1 values                                                                                                                |
| dim2                                | array   | Array of type `INTEGER` of desired dim2 values                                                                                                                |
| dim3                                | array   | Array of type `INTEGER` of desired dim3 values                                                                                                                |
| dim4                                | array   | Array of type `INTEGER` of desired dim4 values                                                                                                                |
| windowStart                         | string  | yyyy-mm-dd format                                                                                                                                             |
| windowEnd                           | string  | yyyy-mm-dd format                                                                                                                                             |
| matchType                           | string  | CoverEntire, OverlapPart, StartWithin, EndWithin                                                                                                              |
| isExact                             | boolean | True for if the window dates should match exactly, False for flexible                                                                                         |
| isExclusive                         | boolean | True for Exclusive, False for Non-Exclusive, null for no value                                                                                                |
| start                               | string  | Record count start (0-based index)                                                                                                                            |
| rows                                | integer | Page result count (25 recommended)                                                                                                                            |
| isWindowingEnforced                 | boolean | Enforce windowing                                                                                                                                             |
| showUnavailable                     | boolean | Show unavailable avails                                                                                                                                       |
| includeUserFriendlyDimensionDisplay | boolean | List out all 4 dimension fields using Excluding format if applicable.                                                                                         |
| templateIds                         | array   | (Optional) - If `recordId` parameter is not included in request, you can specify specific template IDs of the catalog items instead. Array of type `INTEGER`. |
| statusIds                           | array   | (Optional) - If `recordId` parameter is not included in request, you can specify specific status IDs of the catalog items instead. Array of type `INTEGER`.   |
| minWindowDays                       | integer | (Optional) - The minimum availability window in days.                                                                                                         |
| rollupDimId                         | integer | (Optional) - The rights dimension to rollup.                                                                                                                  |
| scopeExclusivity                    | boolean | (Optional) - Scope the results to Exclusivity.                                                                                                                |
| scopeDimensions                     | array   | (Optional) - Scope the results to specific rights dimensions. Array of type `INTEGER`.                                                                        |
| rightsActions                       | array   | (Optional) - Return the rights IDs based on these rights action rules.  Array of type `RightsAction`.                                                         |

{% tabs %}
{% tab title="200: OK The availability for the requested catalog items." %}
```javascript
{
    "invalidCatalogIds": [],
    "rowCount": 1,
    "rows": [
        {
            "dim1": [
                {
                    "id": 1,
                    "value": "All Media",
                    "xref": null
                }
            ],
            "dim2": [
                {
                    "id": 1,
                    "value": "World",
                    "xref": null
                }
            ],
            "dim3": [
                {
                    "id": 1,
                    "value": "All Languages",
                    "xref": null
                }
            ],
            "dim4": null,
            "id": 111,
            "isExclusive": true,
            "lastUpdatedDate": "2018-09-20T11:20:20.260Z",
            "status": {
                "statusId": 1,
                "statusName": "Approved"
            },
            "template": {
                "fields": [],
                "processId": 0,
                "processName": null,
                "templateId": 1,
                "templateName": "Series"
            },
            "title": "Title 111",
            "windowEnd": "2018-09-24",
            "windowStart": "2018-09-01"
        }
    ]
}
```
{% endtab %}

{% tab title="200: OK Some catalogs do not exist, but some do." %}
```json
{
    "invalidCatalogIds": [999,1800],
    "rowCount": 1,
    "rows": [
        {
            "dim1": [
                {
                    "id": 1,
                    "value": "All Media",
                    "xref": null
                }
            ],
            "dim2": [
                {
                    "id": 1,
                    "value": "World",
                    "xref": null
                }
            ],
            "dim3": [
                {
                    "id": 1,
                    "value": "All Languages",
                    "xref": null
                }
            ],
            "dim4": null,
            "id": 111,
            "isExclusive": true,
            "lastUpdatedDate": "2018-09-20T11:20:20.260Z",
            "status": {
                "statusId": 1,
                "statusName": "Approved"
            },
            "template": {
                "fields": [],
                "processId": 0,
                "processName": null,
                "templateId": 1,
                "templateName": "Series"
            },
            "title": "Title 111",
            "windowEnd": "2018-09-24",
            "windowStart": "2018-09-01"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Request object

An API call can be made to this endpoint with a JSON body containing the following parameters:

<table><thead><tr><th width="169.62848014605203">Parameter</th><th width="180.33333333333331">Type</th><th width="186">Description</th><th>Required/Optional</th></tr></thead><tbody><tr><td>recordId</td><td>array of numbers</td><td>entity ids</td><td>Required</td></tr><tr><td>dim1</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>dim2</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>dim3</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>dim4</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>windowStart</td><td>string</td><td>YYYY-MM-DD </td><td>Required</td></tr><tr><td>windowEnd</td><td>string</td><td>YYYY-MM-DD</td><td>Required</td></tr><tr><td>isExclusive</td><td>boolean</td><td>exclusive title flag</td><td>Optional ( defaults to true if not specified )</td></tr><tr><td>matchType</td><td>fixed string values</td><td><p>Valid Values:</p><p>CoverEntire</p><p>OverlapPart</p><p>StartWithin</p><p>EndWithin</p></td><td>Required</td></tr><tr><td>isExact</td><td>boolean</td><td>exact matches</td><td>Optional ( defaults to true if not specified )</td></tr><tr><td>isWindowingEnforced</td><td>boolean</td><td>enforce windowing</td><td>Optional ( defaults to false if not specified )</td></tr><tr><td>showUnavailable</td><td>boolean</td><td>show unavailable avails</td><td>Optional ( defaults to false if not specified )</td></tr><tr><td>start</td><td>number</td><td>start return row ( for pagination )</td><td>Required</td></tr><tr><td>rows</td><td>number</td><td>number of rows to return ( for pagination )</td><td>Required</td></tr><tr><td>truncateDatesToSearch</td><td>boolean</td><td>If true, the windowStart and windowEnd in the response will be truncated to the dates in the request</td><td>Optional ( defaults to false if not specified )</td></tr><tr><td>includeRecalcStatus</td><td>boolean</td><td>If true, a recalcStatus will be returned with the results</td><td>Optional (defaults to false if not specified )</td></tr><tr><td>rightTemplateIds</td><td>array of numbers</td><td>Template IDs of any rights that should be included in the response</td><td>Optional, by default no rights are returned</td></tr><tr><td>includeUserFriendlyDimensionDisplay</td><td>boolean</td><td>If true, a list of each dimension fields will be returned using excluding format if applicable. </td><td>Optional (defaults to false if not specified )</td></tr></tbody></table>

'IncludeUserFriendlyDimensionDisplay': Setting this parameter to true will return additional properties for the dimension data in a general string that will use exclusion logic if that string is shorter than just displaying the list of included items.

* Media example: “All Media Excluding: SVOD”
* Territory example: “Worldwide Excluding: France | Italy | Spain ”
* Language example: “English (US)”
* 4th Dimension, if hierarchical (Channel):“Amazon | Apple TV | Google Play | VUDU”

## Example API request

```json
{
"recordId": [
      36816
  ], 
  "dim1": [],
  "dim2": [],
  "dim3": [],
  "dim4": [], 
  "windowStart": "2021-10-01", 
  "windowEnd": "2021-10-31",   
  "isExclusive": false,
  "matchType": "CoverEntire",
  "isExact": false,
  "start": 0,   
  "rows": 25,
  "includeUserFriendlyDimensionDisplay": true,
  "rightsActions":[
    {
        "reasonUnavailable": "RightsOutExist",
        "rightsActionsTemplateIds":[2],
        "showDimensionLimitation": true,
        "showTermLimitation": true
    }
  ]
}
```

## Response object

On a successful API call ( HTTP Status 200 ) the following information will be returned:

<table><thead><tr><th>Parameter</th><th width="151.33333333333331">Type</th><th>Description</th></tr></thead><tbody><tr><td>invalidRecordIds</td><td>int[]</td><td>A list of catalog item IDs from the request that are invalid. The catalog either does not exist or the API user does not have access to it.</td></tr><tr><td>rowCount</td><td>int</td><td>number of rows returned</td></tr><tr><td>rows</td><td>array of availability objects ( see table below)</td><td>availability data</td></tr><tr><td>recalcStatus</td><td>string</td><td>Only returned if includeRecalc = true in the request. Returns 'calculating' If a recalculation of availabilities is currently underway, 'paused' if that recalculation has been paused, and 'calculated' if availability calculations are up to date.</td></tr><tr><td>rights</td><td>array of right objects</td><td>Distinct list of all rights involved in the availabilities returned. Only returned if rightTemplateIDs were provided in the request.</td></tr></tbody></table>



### **Availability object**

| Parameter          | Type                                        | Description                                                                                                           |
| ------------------ | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| LastUpdatedDate    | string                                      | Last update date / time                                                                                               |
| Template           | template data ( see table below )           | Template data structure                                                                                               |
| Status             | status data ( see table below )             | Status data structure                                                                                                 |
| WindowStart        | YYYY-MM-DD                                  | Start window date                                                                                                     |
| WindowEnd          | YYYY-MM-DD                                  | End window date                                                                                                       |
| Dim1               | array of char data data ( see table below ) | Dimension 1 data                                                                                                      |
| Dim2               | array of char data ( see table below )      | Dimension 2 data                                                                                                      |
| Dim3               | array of char data ( see table below )      | Dimension 3 data                                                                                                      |
| Dim4               | array of char data ( see table below )      | Dimension 4 data                                                                                                      |
| IsExclusive        | bool                                        | Flag for exclusivity                                                                                                  |
| IsExact            | bool                                        | Flag for exact match                                                                                                  |
| Available          | string                                      | Available status                                                                                                      |
| ReasonUnavailable  | string                                      | Reason if unavailable                                                                                                 |
| associatedRightIds | int\[]                                      | Specific rights involved in this availability result. Only returned if rightTemplateIDs were provided in the request. |
| dim1Display        | string                                      | Dimension 1 data using excluding format if applicable.                                                                |
| dim2Display        | string                                      | Dimension 2 data using excluding format if applicable.                                                                |
| dim3Display        | string                                      | Dimension 3 data using excluding format if applicable.                                                                |
| dim4Display        | string                                      | Dimension 4 data using excluding format if applicable.                                                                |



### Entity template object

<table><thead><tr><th>Parameter</th><th width="151.33333333333331">Type</th><th>Description</th></tr></thead><tbody><tr><td>templateId</td><td>number</td><td>Template identifier</td></tr><tr><td>templateName</td><td>string</td><td>Template name</td></tr><tr><td>processId</td><td>number</td><td>Process identifier</td></tr><tr><td>processName</td><td>string</td><td>Process name</td></tr></tbody></table>



### **Entity status object**

<table><thead><tr><th>Parameter</th><th width="151.33333333333331">Type</th><th>Description</th></tr></thead><tbody><tr><td>statusId</td><td>number</td><td>Status identifier</td></tr><tr><td>statusName</td><td>string</td><td>Status name</td></tr></tbody></table>



### **Dimension data object**

| Parameter | Type   | Description                     |
| --------- | ------ | ------------------------------- |
| id        | number | Identifier                      |
| value     | string | Dimension Value                 |
| xref      | string | Dimension Cross Reference Value |



### Rights action object

| Parameter                | Type    | Description                                                                                        |
| ------------------------ | ------- | -------------------------------------------------------------------------------------------------- |
| reasonUnavailable        | string  | The reason unavailable. Possible values can be found [here](../avails-reason-unavailable-list.md). |
| rightsActionsTemplateIds | array   | Array of type `INTEGER` to filter results by right template ID.                                    |
| showDimensionLimitation  | boolean | Show the dimension limitation in the result.                                                       |
| showTermLimitation       | boolean | Show the term limitation in the result.                                                            |

## Example API response

```json
{
  "invalidRecordIds": [],
  "rowCount": 1,
  "rows": [
    {
      "lastUpdatedDate": "2021-10-05T22:41:58.467Z",
      "template": {
        "templateId": 19,
        "templateName": "Movie",
        "processId": 0,
        "processName": null
      },
      "status": {
        "statusId": 11,
        "statusName": "Approved"
      },
      "windowStart": "2021-10-01",
      "windowEnd": "2021-10-15",
      "dim1": [
        {
           "id": 7,
           "value": "Free TV"
           "xref": null
        },
        {
            "id": 10,
            "value": "Theatrical"
            "xref": null
        },
        {
            "id": 18,
            "value": "Hotels"
            "xref": null
        },
        {
            "id": 51,
            "value": "Non-Theatrical / Public Video"
            "xref": null
        },
        {
            "id": 52,
            "value": "Pay Per View"
            "xref": null
        },
        {
            "id": 53,
            "value": "Pay TV"
            "xref": null
        },
        {
            "id": 54,
            "value": "VOD"
            "xref": null
        },
        {
            "id": 59,
            "value": "Derivative/Ancillary"
            "xref": null
       },
       {
            "id": 60,
            "value": "Other"
            "xref": null
        }
      ],
      "dim2": [
        {
          "id": 43,
          "value": "North America",
          "xref": null
        }
      ],
      "dim3": [
        {
          "id": 29,
          "value": "English",
          "xref": "en"
        }
      ],
      "dim4": null,
      "dim1Display": "All Media Excluding: Broadcast TV|Transportation|VOD 1",
      "dim2Display": "North America",
      "dim3Display": "English",
      "dim4Display": "",
      "isExclusive": false,
      "isExact": false,
      "matchType": "CoverEntire",
      "available": "Partially",
      "rightsActions": [125],
      "reasonUnavailable": "Limited (Term)",
      "id": 36816,
      "title": "title"
    }
  ]
}
```

