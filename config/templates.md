# Templates

All template endpoints operate in the same way, the only difference being the entity type name, or `char type`, in the URL (see [Entities](https://app.gitbook.com/s/-M8zuJdsrsd_MeaESXRx-3778137224/entities "mention")). The main list endpoint provides general information about the available templates. For more detailed information on specific templates, including their fields and relationships, you can add the template ID to the URL. To get even more specific details, such as date alerts, conditional fields, parent group, pick list reference, and system indicators, you can append the label of a field to the URL. Refer to the examples below for more information.&#x20;

## Get template list

<mark style="color:green;">`GET`</mark>`https://ris.rightsline.com/v4/[char type]-templates`

Retrieve high level details about the number of templates for a given entity type.

**Headers**

| Name          | Value                   |
| ------------- | ----------------------- |
| x-api-key     | Your company's API key. |
| Authorization | Authentication token.   |

**Response**

{% tabs %}
{% tab title="200" %}


```json
{
    "templates": [
        {
            "templateId": 14,
            "templateName": "Bundle/Pack",
            "templateGroupId": 2,
            "templateGroupName": "Collection",
            "systemIndicatorId": 0,
            "processId": 4,
            "processName": "Catalog Workflow"
        },
        {
            "templateId": 12,
            "templateName": "Series",
            "templateGroupId": 1,
            "templateGroupName": "Property",
            "systemIndicatorId": 0,
            "processId": 4,
            "processName": "Catalog Workflow"
        }
    ]
}
```
{% endtab %}
{% endtabs %}



## Get template details

<mark style="color:green;">`GET`</mark>`https://ris.rightsline.com/v4/[char type]-templates/[template ID]`

Retrieve specific details for a given template

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "fields": [
        {
            "fieldName": "Revision ID",
            "fieldDescription": "Revision ID",
            "label": "entity_revision_id",
            "required": true,
            "reportIndicator": false,
            "maxLength": 50,
            "editable": false,
            "dataType": "AlphaNumericText",
            "allowMultiple": false,
            "sequenceNumber": 1,
            "groupId": 8,
            "groupName": "System",
            "groupSequenceNumber": 1,
            "listOfValues": [],
            "systemIndicatorId": -1,
            "copyIndicator": false
        },
        {
            "fieldName": "Title",
            "fieldDescription": "Name",
            "label": "entity_title",
            "required": true,
            "reportIndicator": false,
            "maxLength": 500,
            "editable": true,
            "dataType": "AlphaNumericText",
            "allowMultiple": false,
            "sequenceNumber": 1,
            "groupId": 3,
            "groupName": "Overview",
            "groupSequenceNumber": 2,
            "listOfValues": [],
            "systemIndicatorId": -1,
            "copyIndicator": true
        },
        {
            "fieldName": "EIDR",
            "fieldDescription": "EIDR",
            "label": "eidr",
            "required": false,
            "reportIndicator": false,
            "maxLength": 29,
            "editable": true,
            "dataType": "AlphaNumericText",
            "allowMultiple": false,
            "sequenceNumber": 1,
            "groupId": 10,
            "groupName": "Business",
            "groupSequenceNumber": 5,
            "listOfValues": [],
            "systemIndicatorId": 0,
            "copyIndicator": true
        },
        {
            "fieldName": "U.S. Release Year",
            "fieldDescription": "Release Year",
            "label": "release_year",
            "required": false,
            "reportIndicator": false,
            "maxLength": 4,
            "editable": true,
            "dataType": "FourDigitYear",
            "allowMultiple": false,
            "sequenceNumber": 1,
            "groupId": 18,
            "groupName": "Film Info",
            "groupSequenceNumber": 6,
            "listOfValues": [],
            "systemIndicatorId": 0,
            "copyIndicator": true
        },
        {
            "fieldName": "Target Market",
            "fieldDescription": "Target Market",
            "label": "target_market",
            "required": false,
            "reportIndicator": false,
            "maxLength": 100,
            "editable": true,
            "dataType": "AlphaNumericText",
            "allowMultiple": false,
            "sequenceNumber": 1,
            "groupId": 19,
            "groupName": "Festival/Market",
            "groupSequenceNumber": 7,
            "listOfValues": [
                {
                    "id": 1,
                    "label": "Sundance",
                    "childValues": []
                },
                {
                    "id": 2,
                    "label": "Berlin",
                    "childValues": []
                },
                {
                    "id": 3,
                    "label": "SXSW",
                    "childValues": []
                },
                {
                    "id": 4,
                    "label": "Tribeca",
                    "childValues": []
                },
                {
                    "id": 5,
                    "label": "Cannes",
                    "childValues": []
                },
                {
                    "id": 6,
                    "label": "Toronto",
                    "childValues": []
                },
                {
                    "id": 7,
                    "label": "AFM",
                    "childValues": []
                }
            ],
            "systemIndicatorId": 0,
            "copyIndicator": true
        },
    ],
    "templateId": 1,
    "templateName": "Feature",
    "templateGroupId": 1,
    "templateGroupName": "Property",
    "systemIndicatorId": 0,
    "processId": 4,
    "processName": "Catalog Workflow",
    "parentRelationships": [
        {
            "charTypeID": 1,
            "templateID": 1,
            "templateName": "Feature",
            "relRecTypeID": 2,
            "relRecTypeDescription": "Rights Relevant"
        },
        {
            "charTypeID": 1,
            "templateID": 12,
            "templateName": "Series",
            "relRecTypeID": 1,
            "relRecTypeDescription": "Non Rights Relevant"
        }
    ],
    "childRelationships": [
        {
            "charTypeID": 1,
            "templateID": 1,
            "templateName": "Feature",
            "relRecTypeID": 2,
            "relRecTypeDescription": "Rights Relevant"
        },
        {
            "charTypeID": 1,
            "templateID": 12,
            "templateName": "Series",
            "relRecTypeID": 1,
            "relRecTypeDescription": "Non Rights Relevant"
        },
        {
            "charTypeID": 1,
            "templateID": 16,
            "templateName": "Element",
            "relRecTypeID": 2,
            "relRecTypeDescription": "Rights Relevant"
        }
    ]
}
```
{% endtab %}

{% tab title="404" %}
```json
{
    "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}



## Get template field details

<mark style="color:green;">`GET`</mark>`/[char type]/templates/[template ID]/[field label]`

Retrieve specific details for a given template's specific field

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "fieldName": "MPAA Rating",
    "fieldDescription": "MPAA Rating",
    "label": "mpaa_rating",
    "required": false,
    "maxLength": 500,
    "editable": true,
    "dataType": "AlphaNumericText",
    "allowMultiple": false,
    "sequenceNumber": 1,
    "groupId": 4,
    "groupName": "Details",
    "pickListId": "d97833a3-77be-eb11-9472-0af1f058195a",
    "pickListName": "Ratings - MPAA",
    "listOfValues": [
        {
            "id": 1,
            "label": "G",
            "childValues": []
        },
        {
            "id": 2,
            "label": "PG",
            "childValues": []
        },
        {
            "id": 3,
            "label": "PG-13",
            "childValues": []
        },
        {
            "id": 4,
            "label": "R",
            "childValues": []
        },
        {
            "id": 5,
            "label": "NC-17",
            "childValues": []
        }
    ],
    "systemIndicatorId": 0,
    "dateAlerts": [],
    "conditionalField": {
        "triggerLabel": "genre",
        "triggerValue": "2"
    }
}
```
{% endtab %}

{% tab title="404" %}
```json
{
    "message": "Resource Not Found"
}
```
{% endtab %}
{% endtabs %}
