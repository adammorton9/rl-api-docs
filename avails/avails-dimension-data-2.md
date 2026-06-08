# Get Snapshot Details

## Get Snapshots

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/snapshots/{guid}`

This endpoint returns a snapshot's details.



{% tabs %}
{% tab title="200 User's snapshots rows" %}
```javascript
[
    {
        "associatedCatalog": {
            "id": 43222,
            "title": "01.26 Episode 105",
            "template": {
                "templateId": 13,
                "templateName": "Episode",
                "templateGroupId": 0,
                "systemIndicatorId": 0,
                "processId": 0
            },
            "status": {
                "statusId": 1,
                "statusName": "Development"
            }
        },
        "media": [
            {
                "id": 10,
                "value": "Theatrical"
            }
        ],
        "territory": [
            {
                "id": 186,
                "value": "France"
            }
        ],
        "language": [
            {
                "id": 38,
                "value": "French"
            }
        ],
        "channel": [
            {
                "id": 2,
                "value": "Apple TV"
            },
            {
                "id": 3,
                "value": "Google Play"
            }
        ],
        "termStart": "2025-01-02T00:00:00.000Z",
        "termEnd": "2025-01-29T00:00:00.000Z",
        "exclusivity": true
    }
]
```
{% endtab %}
{% endtabs %}

