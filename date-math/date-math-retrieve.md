# Retrieve date math

## Get date math

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/:entityType/:entityID/date-math`

This endpoint retrieves date math objects related to an entity.

#### Path Parameters

| Name       | Type    | Description                                                                                |
| ---------- | ------- | ------------------------------------------------------------------------------------------ |
| entityID   | integer | The unique ID of the entity that the date math is related to.                              |
| entityType | string  | The type of entity that the date math is related to. ex: deal, catalog-item, table, etc.   |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Date math successfully retrieved." %}
```javascript
[
  {
    "result": "Contract Term Start earliest of 1/27/2018 and Contract Term End.",
    "dateMathCalcId": 2464929427129109,
    "compareToDate": "2018-01-27T08:00:00.000Z",
    "recalcOption": "Open",
    "conditionOption": "ASAP",
    "childCharacteristic": {
      "type": "Earliest Of",
      "entityTitle": "DealTest84",
      "entityTypeId": 4,
      "id": 3,
      "tagLabel": "contract_term_start",
      "label": "Contract Term Start",
      "characteristicId": 22
    },
    "parentCalcs": [
      {
        "dateMathRelId": 13570,
        "quantity": null,
        "isPriorTo": null,
        "yearQuantity": 0,
        "monthQuantity": 0,
        "weekQuantity": 0,
        "dayQuantity": 15,
        "dayUnit": "Days",
        "sortOrder": 0,
        "entityTitle": "DealTest84",
        "entityTypeId": 4,
        "id": 3,
        "tagLabel": "contract_term_end",
        "label": "Contract Term End",
        "characteristicId": 26
      }
    ]
  }
]
```
{% endtab %}
{% endtabs %}
