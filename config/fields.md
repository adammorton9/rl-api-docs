# Fields

Similar to templates, a complete list of all fields available for a given entity type can be retrieved from the /\*-fields endpoint with entity type name, or `char type`, being part of the URL (see [Entities](https://app.gitbook.com/s/-M8zuJdsrsd_MeaESXRx-3778137224/entities "mention")).&#x20;



## Get Fields

<mark style="color:green;">`GET`</mark> `https://ris.rightsline.com/v4/[char type]-fields`

\<Description of the endpoint>

**Headers**

| Name          | Value                   |
| ------------- | ----------------------- |
| x-api-key     | Your company's API key. |
| Authorization | Authentication token.   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
[
    {
        "fieldName": "Notes",
        "fieldDescription": "Notes",
        "label": "notes",
        "required": false,
        "reportIndicator": true,
        "maxLength": 500,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 1096
    },
    {
        "fieldName": "Currency",
        "fieldDescription": "Currency",
        "label": "currency",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "pickListSourceId": "186364fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Currency",
        "listOfValues": [],
        "systemIndicatorId": 8
    },
    {
        "fieldName": "Due Date",
        "fieldDescription": "Due Date",
        "label": "due_date",
        "required": false,
        "reportIndicator": true,
        "maxLength": 25,
        "editable": false,
        "dataType": "Date_US",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 2009
    },
    {
        "fieldName": "Payment Date",
        "fieldDescription": "Payment Date",
        "label": "payment_date",
        "required": false,
        "reportIndicator": true,
        "maxLength": 25,
        "editable": false,
        "dataType": "Date_US",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Total",
        "fieldDescription": "Total",
        "label": "total",
        "required": false,
        "reportIndicator": true,
        "maxLength": 50,
        "editable": false,
        "dataType": "Currency",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 9
    },
    {
        "fieldName": "Balance",
        "fieldDescription": "Balance",
        "label": "balance",
        "required": false,
        "reportIndicator": true,
        "maxLength": 50,
        "editable": false,
        "dataType": "Currency",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 10
    },
    {
        "fieldName": "Invoice ID",
        "fieldDescription": "Invoice ID",
        "label": "entity_id",
        "required": false,
        "reportIndicator": true,
        "maxLength": 50,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": -1
    },
    {
        "fieldName": "Revision ID",
        "fieldDescription": "Revision ID",
        "label": "entity_revision_id",
        "required": false,
        "reportIndicator": true,
        "maxLength": 50,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": -1
    },
    {
        "fieldName": "Invoice Title",
        "fieldDescription": "Invoice Title",
        "label": "entity_title",
        "required": false,
        "reportIndicator": true,
        "maxLength": 5000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": -1
    },
    {
        "fieldName": "Template",
        "fieldDescription": "Template",
        "label": "entity_template",
        "required": false,
        "reportIndicator": true,
        "maxLength": 1000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": -1
    },
    {
        "fieldName": "Status",
        "fieldDescription": "Status",
        "label": "entity_status",
        "required": false,
        "reportIndicator": true,
        "maxLength": 1000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": -1
    },
    {
        "fieldName": "Alpha Numeric Text",
        "fieldDescription": "",
        "label": "alpha_numeric_text",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Alpha Numeric Text Single Select LOV",
        "fieldDescription": "",
        "label": "alpha_numeric_text_single_select_lov",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "pickListSourceId": "eb6264fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": " Audio Bitrate Kbps",
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Alpha Numeric Text Multi Select LOV",
        "fieldDescription": "",
        "label": "alpha_numeric_text_multi_select_lov",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": true,
        "pickListSourceId": "eb6264fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": " Audio Bitrate Kbps",
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Checkbox",
        "fieldDescription": "",
        "label": "checkbox",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Checkbox",
        "allowMultiple": false,
        "pickListSourceId": "086364fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Yes/No",
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Date",
        "fieldDescription": "",
        "label": "date",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Date_US",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Email",
        "fieldDescription": "",
        "label": "email",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Email",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "External Document",
        "fieldDescription": "",
        "label": "external_document",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "ExternalDocument",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "4 Digit Year",
        "fieldDescription": "",
        "label": "4_digit_year",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "FourDigitYear",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Internet Address",
        "fieldDescription": "",
        "label": "internet_address",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "InternetAddress",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Money",
        "fieldDescription": "",
        "label": "money",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Money",
        "allowMultiple": false,
        "pickListSourceId": "186364fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Currency",
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Number",
        "fieldDescription": "",
        "label": "number",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Number",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Percentage",
        "fieldDescription": "",
        "label": "percentage",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Percentage",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Time Code",
        "fieldDescription": "",
        "label": "time_code",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "SMPTETimeCode",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 0
    },
    {
        "fieldName": "Transaction Date",
        "fieldDescription": "",
        "label": "transaction_date",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Date_US",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 12
    },
    {
        "fieldName": "Balance (Money)",
        "fieldDescription": "",
        "label": "balance_money",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Money",
        "allowMultiple": false,
        "pickListSourceId": "186364fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Currency",
        "listOfValues": [],
        "systemIndicatorId": 10
    },
    {
        "fieldName": "Total (Money)",
        "fieldDescription": "",
        "label": "total_money",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Money",
        "allowMultiple": false,
        "pickListSourceId": "186364fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Currency",
        "listOfValues": [],
        "systemIndicatorId": 9
    },
    {
        "fieldName": "Full Recoupment Date",
        "fieldDescription": "",
        "label": "full_recoupment_date",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Date_US",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 2012
    },
    {
        "fieldName": "Income Group",
        "fieldDescription": "",
        "label": "income_group",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": true,
        "pickListSourceId": "e46264fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Media",
        "listOfValues": [],
        "systemIndicatorId": 13
    },
    {
        "fieldName": "Territory",
        "fieldDescription": "",
        "label": "territory",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": true,
        "pickListSourceId": "016364fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Territory Master",
        "listOfValues": [],
        "systemIndicatorId": 2
    },
    {
        "fieldName": "Term Start",
        "fieldDescription": "",
        "label": "term_start",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Date_US",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 5
    },
    {
        "fieldName": "Term End",
        "fieldDescription": "",
        "label": "term_end",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "Date_US",
        "allowMultiple": false,
        "listOfValues": [],
        "systemIndicatorId": 6
    },
    {
        "fieldName": "Title Category",
        "fieldDescription": "",
        "label": "title_category",
        "required": false,
        "reportIndicator": true,
        "maxLength": 10000,
        "editable": false,
        "dataType": "AlphaNumericText",
        "allowMultiple": false,
        "pickListSourceId": "256364fa-5253-ed11-9485-0af1f058195a",
        "pickListSourceName": "Title Category",
        "listOfValues": [],
        "systemIndicatorId": 2072
    }
]
```
{% endtab %}
{% endtabs %}
