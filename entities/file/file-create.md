# Create a file

## Create file

<mark style="color:green;">`POST`</mark> `https://ris.rightsline.com/v4/file`

This endpoint allows you to create a new file.

#### Headers

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

#### Request Body

| Name                | Type   | Description                                          |
| ------------------- | ------ | ---------------------------------------------------- |
| title               | string | The title of the new file.                           |
| template            | object | The template of the new file.                        |
| template.templateId | string | The unique ID of the template to assign to the file. |
| characteristics     | object | The field values to assign to the file.              |
| parentRelationship  | array  | Create this file as a child of a deal.               |

{% tabs %}
{% tab title="200 File created successfully.  Returns the ID of the entity and the URL to upload the file." %}
```javascript
{
    "id": 2687,
    "link": {
        "url": "https://de324y6j768fq1.cloudfront.net/************",
        "expiration": "2021-04-20T22:44:58.314Z"
    }
}
```
{% endtab %}

{% tab title="400 Request is missing required information, or the information is invalid." %}
```javascript
{
  "message": "TemplateId is required"
}
```
{% endtab %}
{% endtabs %}

## Example: Upload a file

### 1. Create file in Rightsline

POST: https://ris.rightsline.com/v4/file (NOTE: `file_name` char is **required**)

```javascript
{
    "title": "Test File",
    "template": {
        "templateId": 1
    },
    "characteristics": {
        "file_name": "final.pdf",
        "notes": "This document has been signed",
        "date_signed":"2020-01-31"
    },
    "parentRelationship": [
        {
            "parentCharTypeId": 4,
            "parentRecordId": 100
        }
    ]
}
```

A successful response will return the following payload:

```javascript
{
    "id": 2687,
    "link": {
        "url": "https://*********.cloudfront.net/************",
        "expiration": "2021-04-20T22:44:58.314Z"
    }
}
```

You will use the `url` in the response body to upload the file.

### 2. Upload file data

When uploading the file, you do not need to include any Authorization header, as the URL is already authorized to upload to the specified location.

```coffeescript
PUT https://*********.cloudfront.net/************ \
  --data *file binary*
```
