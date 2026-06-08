# DateMath

{% hint style="info" %}
GraphQL can significantly enhance the power of your API Integration. To onboard, please reach out to your Account Manager for pricing information.
{% endhint %}

**DateMath** is a field on the [Entity](./) root type that represents any characteristics that are set up with DateMath on a given Rightsline record.  DateMath is an array of objects with the following structure:

```graphql
{
    entity(id: 1, charTypeId: 4) {
        dateMath {
            result
            dateMathCalcId
            isCalculated
            compareToDate
            dateOption
            recalcOption
            conditionOption
            parentCalcs {
                dateMathRelId
                yearQuantity
                monthQuantity
                weekQuantity
                dayQuantity
                dayUnit
                isPriorTo
                sortOrder
                entityTitle
                entityTypeId
                id
                tagLabel
                label
                characteristicId
            }
            childCharacteristic {
                type
                entityTitle
                entityTypeId
                id
                tagLabel
                label
                characteristicId
            }
        }
    }
}
```

The response for a record's DateMath will look like the following:

```json
{
    "data": {
        "entity": {
            "dateMath": [
                {
                    "result": "Agreement Date equals Execution Date.",
                    "dateMathCalcId": 2145648462165,
                    "isCalculated": true,
                    "compareToDate": null,
                    "dateOption": null,
                    "recalcOption": "Archive",
                    "conditionOption": "ASAP",
                    "parentCalcs": [
                        {
                            "dateMathRelId": 12345,
                            "yearQuantity": null,
                            "monthQuantity": null,
                            "weekQuantity": null,
                            "dayQuantity": null,
                            "dayUnit": "Days",
                            "isPriorTo": false,
                            "sortOrder": 0,
                            "entityTitle": "Test Deal 2",
                            "entityTypeId": 4,
                            "id": 2,
                            "tagLabel": "execution_date",
                            "label": "Execution Date",
                            "characteristicId": 200
                        }
                    ],
                    "childCharacteristic": {
                        "type": "Equals",
                        "entityTitle": "Test Deal 1",
                        "entityTypeId": 4,
                        "id": 1,
                        "tagLabel": "agreement_date",
                        "label": "Agreement Date",
                        "characteristicId": 191
                    }
                }
            ]
        }
    }
}
```
