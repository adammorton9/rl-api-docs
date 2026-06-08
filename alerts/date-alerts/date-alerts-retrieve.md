# Retrieve date alerts

## Get list of date alerts

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/:entityType/:entityID/date-alerts`

This endpoint retrieves a list of all the date alerts for all characteristics on the entity.

#### Path Parameters

| Name                                         | Type    | Description                                                                                |
| -------------------------------------------- | ------- | ------------------------------------------------------------------------------------------ |
| entityID<mark style="color:red;">\*</mark>   | integer | The unique ID of the entity that the date math is related to.                              |
| entityType<mark style="color:red;">\*</mark> | string  | The type of entity that the date math is related to. ex: deal, catalog-item, table, etc.   |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200 Date alerts successfully retrieved." %}
```javascript
[
  {
    "id": "7f37e0d2-7da0-4504-a250-46c9bded40b5",
    "tagLabel": "original_air_date",
    "charId": 197,
    "value": "",
    "deliveryDate": {
      "label": "When Original Air Date is first set or updated."
    },
    "deliveryOptions": {
      "emailNotification": false,
      "calendarInvite": true,
      "doNotSendIfRecordIsInactive": false,
      "triggerSnsOrSqs": false
    },
    "subject": "Catalog Module: Date Alert and Merge tag Notif",
    "body": "",
    "bodyHtml": "<p>html body here</p>",
    "recipients": {
      "emailAddresses": [
        "ttoth@rightsline.com"
      ],
      "roles": [],
      "parties": []
    }
  },
  {
    "id": "3d10cec1-0a41-4489-bcf3-c3a5a8d2144e",
    "tagLabel": "original_air_date",
    "charId": 197,
    "value": "",
    "deliveryDate": {
      "label": "When Original Air Date is first set or updated."
    },
    "deliveryOptions": {
      "emailNotification": true,
      "calendarInvite": false,
      "doNotSendIfRecordIsInactive": false,
      "triggerSnsOrSqs": false
    },
    "subject": "Rightsline Date Alert - 49264 - Test JT 2.15 Season 02 Episode 03 Pilot 01",
    "body": "",
    "bodyHtml": "new custom alert",
    "recipients": {
      "emailAddresses": [
        "ttoth@rightsline.com",
        "tim.toth13@gmail.com"
      ],
      "roles": [],
      "parties": []
    }
  },
  {
    "id": "ccc050a2-3d9f-41ea-88f4-8862aca17500",
    "tagLabel": "original_air_date",
    "charId": 197,
    "value": "",
    "deliveryDate": {
      "label": "4 Weeks After Original Air Date AND AS Char Date 2 Contains Value",
      "quantity": 4,
      "frequency": 2,
      "frequencyLabel": "Weeks",
      "timeFrame": 3,
      "timeFrameLabel": "After",
      "deliveryConditional": {
        "charId": 219,
        "tagLabel": "as_char_date_2_end",
        "condition": 0,
        "conditionLabel": "Contains Value"
      }
    },
    "deliveryOptions": {
      "emailNotification": true,
      "calendarInvite": false,
      "doNotSendIfRecordIsInactive": false,
      "triggerSnsOrSqs": false
    },
    "subject": "Catalog Module: Date Alert and Merge tag Notif",
    "body": "",
    "bodyHtml": "<p>html body goes here</p>",
    "recipients": {
      "emailAddresses": [
        "ttoth@rightsline.com"
      ],
      "roles": [
        "27",
        "26",
        "25"
      ],
      "parties": [
        "2",
        "3",
        "14"
      ]
    }
  },
  {
    "id": "0ee35892-6aa6-4f49-801c-27554d48ec41",
    "tagLabel": "original_air_date",
    "charId": 197,
    "value": "",
    "deliveryDate": {
      "label": "1 Weeks After Original Air Date AND Release Date Contains Value",
      "quantity": 1,
      "frequency": 2,
      "frequencyLabel": "Weeks",
      "timeFrame": 3,
      "timeFrameLabel": "After",
      "deliveryConditional": {
        "charId": 195,
        "tagLabel": "release_date",
        "condition": 0,
        "conditionLabel": "Contains Value"
      }
    },
    "deliveryOptions": {
      "emailNotification": true,
      "calendarInvite": true,
      "doNotSendIfRecordIsInactive": true,
      "triggerSnsOrSqs": false
    },
    "subject": "Rightsline Date Alert - 49264 - Test JT 2.15 Season 02 Episode 03 Pilot 01",
    "body": "totally regular body",
    "bodyHtml": "Totally Custom Alert with 2 Weeks After Notify AND Release Date Has Value",
    "recipients": {
      "emailAddresses": [
        "ttoth@rightsline.com",
        "tim.toth13@gmail.com"
      ],
      "roles": [
        "25",
        "26",
        "27"
      ],
      "parties": [
        "2",
        "3"
      ]
    }
  }
]
```
{% endtab %}

{% tab title="200: OK Date alerts successfully retrieved, none." %}
```json
[]
```
{% endtab %}

{% tab title="404: Not Found " %}
```json
{
    "message": "No entity with id: d29c1r1839102"
}
```
{% endtab %}
{% endtabs %}
