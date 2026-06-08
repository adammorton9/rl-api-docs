# Is catalog item available

## Get title availability

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/avails/is-title-available`

This endpoint returns the availability for a single catalog item.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name        | Type    | Description                                                           |
| ----------- | ------- | --------------------------------------------------------------------- |
| recordId    | integer | The ID of the catalog item                                            |
| dim1        | array   | Array of type `INTEGER` of desired dim1 values                        |
| dim2        | array   | Array of type `INTEGER` of desired dim2 values                        |
| dim3        | array   | Array of type `INTEGER` of desired dim3 values                        |
| dim4        | array   | Array of type `INTEGER` of desired dim4 values                        |
| windowStart | string  | yyyy-mm-dd format                                                     |
| windowEnd   | string  | yyyy-mm-dd format                                                     |
| matchType   | string  | CoverEntire, OverlapPart, StartWithin, EndWithin                      |
| isExact     | boolean | True for if the window dates should match exactly, False for flexible |
| isExclusive | boolean | True for Exclusive, False for Non-Exclusive, null for no value        |
| start       | string  | Record count start (0-based index)                                    |
| rows        | integer | Page result count (25 recommended)                                    |

{% tabs %}
{% tab title="200: OK The availability of the catalog item." %}
```javascript
{
    "invalidRecordIds": [],
    "isAvailable": true,
    "isExclusive": true
}
```
{% endtab %}

{% tab title="200: OK Catalog item does not exist, or user does not have access." %}
```json
{
    "invalidRecordIds": [1288],
    "isAvailable": false,
    "isExclusive": false
}
```
{% endtab %}
{% endtabs %}

An API call can be made to this endpoint with a JSON body containing the following parameters:

<table><thead><tr><th>Parameter</th><th width="184.33333333333331">Type</th><th>Description</th><th>Required/Optional</th></tr></thead><tbody><tr><td>recordId</td><td>number</td><td>entity id</td><td>Required</td></tr><tr><td>dim1</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>dim2</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>dim3</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>dim4</td><td>array of numbers</td><td>Dimension Values</td><td>Optional</td></tr><tr><td>windowStart</td><td>string</td><td>YYYY-MM-DD </td><td>Required</td></tr><tr><td>windowEnd</td><td>string</td><td>YYYY-MM-DD</td><td>Required</td></tr><tr><td>isExclusive</td><td>boolean</td><td>exclusive title flag</td><td>Optional ( defaults to true if not specified )</td></tr><tr><td>includeRecalcStatus</td><td>boolean</td><td>If true, a recalcStatus will be returned with the results</td><td>Optional ( defaults to false if not specifiec )</td></tr></tbody></table>



Example API call body:

```json
{
  "recordId": 1288,
  "dim1": [2,3],
  "dim2": [1],
  "dim3": [4],
  "windowStart": "2018-12-22", 
  "windowEnd": "2019-12-22",
}
```



**Response**

On a successful API call ( HTTP Status 200 ) the following information will be returned:

<table><thead><tr><th>Parameter</th><th width="151.33333333333331">Type</th><th>Description</th></tr></thead><tbody><tr><td>invalidRecordIds</td><td>int[]</td><td>List of catalog item IDs that are invalid from the request. The catalog item either does not exist or the API user does not have access to it.</td></tr><tr><td>isAvailable</td><td>boolean</td><td>True if the title is available</td></tr><tr><td>isExclusive</td><td>boolean</td><td>True if the title is exclusive</td></tr><tr><td>recalcStatus</td><td>string</td><td>Only returned if includeRecalc = true in the request. Returns 'calculating' If a recalculation of availabilities is currently underway, 'paused' if that recalculation has been paused, and 'calculated' if availability calculations are up to date.</td></tr></tbody></table>

Example API response:

```json
{
  "invalidRecordIds": [],
  "isAvailable": true,
  "isExclusive": false
}
```
