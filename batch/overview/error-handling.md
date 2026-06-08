# Error handling

### Retrieving a record that does not exist

Request

```json
{
    "method": "GET",
    "records": {
        "1": [
            {
                "id":999999
            }
        ]
    }
}
```

Response

```json
{
    "batchId": 130625454,
    "batchStatus": "Complete",
    "batchResults": {
        "records": {
            "1": [
                {
                    "code": 404,
                    "message": "Record Not Found.",
                    "id": 999999
                }
            ]
        },
        "relationships": []
    }
}
```

### Executing a workflow action that is not available from the current status

Request

```json
{
    "method": "EXECUTE-WORKFLOW",
    "records": {
        "1": [
            {
                "id": 5,
                "actionId":95
            }
        ]
    }
}
```

Response

```json
{
    "batchId": 130625457,
    "batchStatus": "Complete",
    "batchResults": {
        "records": {
            "1": [
                {
                    "code": 403,
                    "message": "Action 95 not available to be taken from status 16",
                    "id": 5
                }
            ]
        },
        "relationships": []
    }
}
```

### Creating a relationship where one of the records does not exist

Request

```json
{
    "method": "POST",
    "records": {
    },
    "relationships":[
        {
            "parentCharTypeId": 4,
            "parentRecordId": 4958,
            "childCharTypeId": 1,
            "childRecordId": 9999999
        }
    ]
}
```

Response

```json
{
    "batchId": 123592183,
    "batchStatus": "Complete",
    "batchResults": {
        "records": {
            "1": [
                {
                    "code": 404,
                    "message": "Record Not Found.",
                    "id": 9999999
                }
            ]
        },
        "relationships": []
    }
}
```
