# Search contract scopes

`POST` `https://ris.rightsline.com/v4/contract-scope/search`

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Query Parameters**

| Name         | Type    | Description                                                                     |
| ------------ | ------- | ------------------------------------------------------------------------------- |
| extendedData | boolean | When `true`, returns additional field metadata alongside characteristic values. |

**Request Body**

| Name  | Type    | Description                                                                                                          |
| ----- | ------- | -------------------------------------------------------------------------------------------------------------------- |
| query | object  | Search criteria. See [Search fields](https://api-docs.rightsline.com/search/search-fields.md) for available filters. |
| start | integer | Zero-based offset for pagination.                                                                                    |
| rows  | integer | Number of results to return (1–100).                                                                                 |

```
{
  "numFound": 1,
  "entities": [
    {
      "id": 1,
      "title": "Contract Scope Title",
      "template": {},
      "status": {},
      "characteristics": {}
    }
  ]
}

```
