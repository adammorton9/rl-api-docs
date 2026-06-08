# Create date math

## Create date math

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/date-math`

This endpoint allows you to create a new date math object.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name              | Type    | Description                                                                 |
| ----------------- | ------- | --------------------------------------------------------------------------- |
| childTagLabel     | string  | The date characteristic to assign the date math.                            |
| childEntityTypeId | integer | The entity type of the record to assign the date math.                      |
| childId           | integer | The ID of the record to assign the date math.                               |
| parentCalcs       | array   | The parent entities on which the date math calculation is based. See below. |

{% tabs %}
{% tab title="200 Date math successfully created.  Returns the ID of the date math object." %}
```
1549444450
```
{% endtab %}
{% endtabs %}

### ParentCalc object

```javascript
{
    "entityTypeId":4, // char type ID
    "id":618, // record ID
    "tagLabel": "contract_term_start", // tag label of source characteristic
    "yearQuantity": 0, // quantity in years
    "monthQuantity": 0, // quantity in months
    "weekQuantity": 0, // quantity in weeks
    "dayQuantity": 15, // quantity in days
    "dayUnit": "Days", // unit for days (Days/BusinessDays)
    "isPriorTo": false, // before or after source date
    "sortOrder": 1 // order in which date is calculated
}
```

### Example

Calculate the `contract_term_end` for deal record 618 as the earliest of the following two source dates:

1. 15 days prior to the `contract_date` of deal record 620, or
2. 15 days after (isPriorTo = false) the `contract_term_start` date on deal 621.

```javascript
{
   "type":"EARLIESTOF",
   "childEntityTypeId":4,
   "childId":618,
   "childTagLabel":"contract_term_end",
   "recalcOption":"OPEN",
   "parentCalcs":[
      {
         "entityTypeId":4,
         "id":620,
         "tagLabel": "contract_date",
         "dayQuantity": 15,
         "dayUnit": "DAYS",
         "isPriorTo": true,
         "sortOrder": 0
      },
      {
         "entityTypeId":4,
         "id":621,
         "tagLabel": "contract_term_start",
         "dayQuantity": 15,
         "dayUnit": "DAYS",
         "isPriorTo": false,
         "sortOrder": 1
      }
   ]
}
```
