# Retrieve all rights in catalog hierarchy

## Get rights in catalog hierarchy

<mark style="color:blue;">`GET`</mark> `https://ris.rightsline.com/v4/catalog-item/:id/rights-in-hierarchy`

This endpoint allows you to retrieve all rights in a catalog hierarchy.

#### Path Parameters

| Name | Type   | Description             |
| ---- | ------ | ----------------------- |
| id   | string | ID of the catalog-item. |

#### Query Parameters

| Name  | Type | Description                                          |
| ----- | ---- | ---------------------------------------------------- |
| start | int  | Index of first record to return in response.         |
| rows  | int  | Number of rows to return in response. Default = 100. |

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

{% tabs %}
{% tab title="200: OK Rights in hierarchy successfully received." %}
```javascript
{
    "numFound": 2,
    "entities": [
        {
            "associationSource": "Explicit | Implicit",
            "impactsAvails": true,
            "id": 1,
            "revisionId": 0,
            "title": "A Rights In",
            "template": {
                "templateId": 1,
                "templateName": "Rights In",
                "processId": 0,
                "processName": null
            },
            "status": {
                "statusId": 1,
                "statusName": "Active"
            },
            "characteristics": {
                "media_right": [
                    {
                        "id": 2,
                        "value": "All Media"
                    }
                ],
                "actual_term_start": "2000-01-01"
            },
            "comments": null,
            "createdById": 10,
            "createdDate": null,
            "lastUpdatedById": 10,
            "lastUpdatedDate": "2022-12-13T18:17:33.540Z",
            "statusUpdatedById": 10,
            "statusUpdatedDate": "2022-12-13T18:17:33.540Z"
        },
        {
            "associationSource": "Implicit",
            "impactsAvails": true,
            "id": 2,
            "revisionId": 0,
            "title": "A Rights In",
            "template": {
                "templateId": 1,
                "templateName": "Rights In",
                "processId": 0,
                "processName": null
            },
            "status": {
                "statusId": 1,
                "statusName": "Active"
            },
            "characteristics": {
                "media_right": [
                    {
                        "id": 2,
                        "value": "All Media"
                    }
                ],
                "actual_term_start": "2021-01-01"
            },
            "comments": null,
            "createdById": 10,
            "createdDate": null,
            "lastUpdatedById": 10,
            "lastUpdatedDate": "2022-10-12T14:40:08.563Z",
            "statusUpdatedById": 10,
            "statusUpdatedDate": "2021-01-08T03:35:05.693Z"
        }
    ]
}
```
{% endtab %}

{% tab title="403: Forbidden Feature flag is not enabled." %}
```json
{
    "message": "Feature flag is not enabled for this function."
}    
```
{% endtab %}

{% tab title="404: Not Found Catalog not found." %}
```json
{
    "message": "Resource Not Found."
}
```
{% endtab %}
{% endtabs %}
