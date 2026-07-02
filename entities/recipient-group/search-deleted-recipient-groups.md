# Search Deleted Recipient Groups

`POST` `https://ris.rightsline.com/v4/recipient-group/search-deleted`

**Headers**

| Name           | Type   | Description             |
| -------------- | ------ | ----------------------- |
| x-api-key      | string | Your company's API key. |
| Authentication | string | Authentication token.   |

**Request Body**

| Name        | Type    | Description                                                          |
| ----------- | ------- | -------------------------------------------------------------------- |
| startDate\* | string  | Start of the deletion date range (ISO 8601).                         |
| endDate\*   | string  | End of the deletion date range (ISO 8601). Maximum range is 30 days. |
| start       | integer | Zero-based offset for pagination.                                    |
| rows        | integer | Number of results to return.                                         |

