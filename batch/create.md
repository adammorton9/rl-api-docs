# Create a batch

## Create batch

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/batch`

Create a new batch for processing.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name          | Type             | Description                                                                                  |
| ------------- | ---------------- | -------------------------------------------------------------------------------------------- |
| method        | string           | GET/POST/PUT/DELETE. See _Batch methods_.                                                    |
| batchOptions  | object           | Options for processing. See _Batch options_.                                                 |
| records       | keyed collection | The records to process.  A key-value collection of the char type ID and an array of records. |
| relationships | array            | The relationships to process.                                                                |

{% tabs %}
{% tab title="202 Batch successfully created." %}
```javascript
{
    "batchId": 48865381,
    "batchStatus": "Created"
}
```
{% endtab %}

{% tab title="429: Too Many Requests Max batches processing reached." %}
```json
{
    "message": "Too many batches in queued status. Please wait and try again."
}
```
{% endtab %}
{% endtabs %}

### Sample Create Batch request - Retrieve records

```javascript
{
    "method": "GET",
    "batchOptions": {
        "cancelIfRecordFails": false
    },
    "records": {
        "1": [
            {
                "id": 100
            },
            {
                "id": 101
            }
        ],
        "3": [
            {
                "id": 200
            },
            {
                "id": 201
            }
        ]
    },
    "relationships": [
        {
            "id": 301
        }
    ]
}
```

### Sample Create Batch Request - Create contact records

When creating records in a batch, you can include an optional string parameter `referenceId` in the request body. If a record in the batch fails to create for any reason, the `referenceId` will be returned for that record so you are able to map the record in the request to the errored record in the response.

<pre class="language-javascript"><code class="lang-javascript">{
    "method": "POST",
<strong>    "records": {
</strong>        "2": [
            {
                "title":"Person 1",
                "template":{
                    "templateId": 1
                },
                "characteristics":{
                    "first_name": "John",
                    "last_name": "Smith",
                    "department": "Sales"
                },
                "referenceId": "contact1"
            },
            {
                "title":"Person 2",
                "template":{
                    "templateId": 1
                },
                "characteristics":{
                    "first_name": "Susan",
                    "last_name": "Williams",
                    "department": "Accounting"
                },
                "referenceId": "contact2"
            }
        ]
    },
    "batchOptions":{
        "cancelIfRecordFails": true
    }
}
</code></pre>

#### Sample Error Response

```json
{
    "batchId": 188181886,
    "batchStatus": "Errored",
    "batchResults": {
        "records": {
            "2": [
                {
                    "code": 400,
                    "message": "{\"IsValid\":false,\"IsLocked\":false,\"IsDeletable\":false,\"Errors\":[{\"Key\":\"CharDataValidation\",\"Value\":[\"Invalid field found fake_field.\"]}],\"HasConflicts\":false,\"HasBlockingConflicts\":false,\"DbValidationErrors\":[]}",
                    "id": 0,
                    "referenceId": "contact1"
                }
            ]
        },
        "relationships": []
    }
}
```

### Sample Create Batch Request - Copy Record

To copy a record or multiple records, you can use the "COPY" method.  Copying a record creates an identical record to the one being copied, with the same char type, template, status, and characteristics.  The new record will have a new ID, and you can specify the following options:

* `title` - The title for the new record
* `dateMathOption (optional, default = Default)` - Use one of the following options:
  * `Default` - All fields with date math on module records will refer to copied record dates; all fields with date math on component record dates will refer to original record dates.
  * `Original Record` - All date math on module record and child components being copied should refer to original record dates.
  * `Copied Record` - All date math on module record and child components being copied should refer to copied record dates.
* `copyRelationships` - include the relationships that you want to copy over to the new record,
* `copyParties` - set to false to discard all parties when copying record. Defaults to true.

```json
{
    "method": "COPY",
    "records": {
        "2": [
            {
                "copyRelationships": [
                    {
                        "id": 971252653,
                        "relationshipType": {
                            "relationshipTypeId": 0,
                            "relationshipTypeName": "Default"
                        },
                        "parentCharTypeId": 4,
                        "parentRecordId": 4123,
                        "parentTemplate": {
                            "templateId": 1,
                        },
                        "childCharTypeId": 2,
                        "childRecordId": 402
                    }
                ],
                "title":"New Title of Record",
                "id": 402,
                "template":{
                    "templateId": 1
                },
                "dateMathOption": "Default", // "Default", "OriginalRecord", or "CopiedRecord"
                "copyParties": true // Defaults to true, set to false to discard parties
            }
        ]
    },
    "batchOptions":{
        "cancelIfRecordFails": true
    }
}
```

### Sample Create Batch Request - Copy To

The Copy To functionality allows you to copy records to a new char type.  The request is the same as the Copy functionality, but including the new charTypeId and the new templateId for the copied record.  The example below copies a catalog item with ID 402 into a new deal.

```json
{
    "method": "COPY",
    "records": {
        "1": [
            {
                "copyRelationships": [],
                "charTypeId": 4,
                "title":"New Title of Record",
                "id": 402,
                "template":{
                    "templateId": 12
                },
                "characteristics":{},
                "dateMathOption": "Default", // "Default", "OriginalRecord", or "CopiedRecord"
                "copyParties": true // Defaults to true, set to false to discard parties
            }
        ]
    },
    "batchOptions":{
        "cancelIfRecordFails": true
    }
}
```

### Sample Create Batch Request - Execute Workflow

```javascript
{
    "method": "EXECUTE-WORKFLOW",
    "records": {
        "1": [
            {
                "id": 100,
                "actionId": 1
            },
            {
                "id": 101,
                "actionId": 1
            }
        ],
        "3": [
            {
                "id": 200,
                "actionId": 2
            },
            {
                "id": 201,
                "actionId": 4
            }
        ]
    }
}
```

### Sample Create Batch Request - Create Relationship

```json
{
    "method": "POST",
    "relationships": [
        {
            "parentCharTypeId": 4,
            "parentRecordId": 4156,
            "childCharTypeId": 3,
            "childRecordId": 131262
        },
        {
            "parentCharTypeId": 4,
            "parentRecordId": 4156,
            "childCharTypeId": 3,
            "childRecordId": 131604
        },
        {
            "parentCharTypeId": 4,
            "parentRecordId": 4156,
            "childCharTypeId": 3,
            "childRecordId": 1324213
        }
    ]
}
```

### Sample Create Batch request - Delete relationships

```javascript
{
    "method": "DELETE",
    "batchOptions": {
        "cancelIfRecordFails": false
    },
    "relationships": [
        {
            "id": 44809801
        },
        {
            "id": 55489923
        }
    ]
}
```

### Sample Create Batch Request - Calculate Amortization

```json
{
    "method": "CALCULATE-AMORTIZATION",
    "amortizationModelId": 1,
    "records": {
        "5": [
            {
                "id": 200
            },
            {
                "id": 201
            }
        ]
    }
}
```
