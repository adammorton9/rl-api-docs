# Update date math

## Update date math

<mark style="color:orange;">`PUT`</mark> `https://ris.rightsline.com/v4/date-math`

This endpoint allows you to update a date math calculation.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name              | Type    | Description                                                                       |
| ----------------- | ------- | --------------------------------------------------------------------------------- |
| dateMathCalcId    | integer | The date math calculation ID to update.                                           |
| type              | string  | Equals (default), EarliestOf, LatestOf, or PriorityOf                             |
| compareToDate     | string  | The date to compare for new date math calculations.                               |
| recalcOption      | string  | Hard (default), Archive, or Open                                                  |
| conditionOption   | string  | ASAP (default), or KeepTBD                                                        |
| createParentCalcs | array   | An array of new parent calculations to add to the existing date math calculation. |
| updateParentCalcs | array   | An array of parent calculations to update on the existing date math calculation.  |
| deleteParentCalcs | array   | Array of type `INTEGER` of the date math calcul                                   |

{% tabs %}
{% tab title="200 Date math updated successfully." %}
```javascript
{    
    "message": "Date math updated successfully."
}
```
{% endtab %}

{% tab title="500 Error updating date math calculation." %}
```javascript
{    
    "message": "We encountered an error while attempting to update date math."
}
```
{% endtab %}
{% endtabs %}

