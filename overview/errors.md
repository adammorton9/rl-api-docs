---
description: Possible error responses that you may receive from the API.
---

# Errors

All exceptions are trapped and logged at the Service Level. The services are designed to always return a response, even in the event of an exception. Standard HTTP response codes will be returned where applicable, for example, unauthorized requests will typically be responded to with a HTTP 401 Unauthorized.

When applicable, additional response information will be provided, including a custom header x-ris-request-id which we can use to look up any API request made and further trouble shoot any issues. In the event that required fields are missing or incorrectly typed data was passed in a request, the validation errors will be returned along with the 400 Bad Request response code.

All error response information contains:

* An appropriate 3xx, 4xx, or 5xx HTTP status code
* Error object containing additional information if applicable

### **Response Elements**

| NAME            | DESCRIPTION                                                            |
| --------------- | ---------------------------------------------------------------------- |
| Code            | The error code is a string that uniquely identifies an error condition |
| Message         | The textual representation of the error that is more human readable    |
| x-ris-requestID | Uniquely identifies the request that resulted in error                 |

### **Handling Errors**

Our API bindings can raise exceptions for many reasons, such as invalid parameters, authentication errors, and network unavailability. We recommend always trying to gracefully handle exceptions from our API.

### **Common Error Codes**

| Error Code | Description           | How to fix                                                                                                                                                                                                      |
| ---------- | --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 400        | Bad Request           | A message will be returned in the response with details on how to modify your request.                                                                                                                          |
| 401        | Unauthorized          | Verify your credentials and authorization signature is correct.                                                                                                                                                 |
| 403        | Permission Denied     | Verify you have the correct permissions enabled in Rightsline to access/create the record.                                                                                                                      |
| 404        | Not Found             | Modify the ID of the record you are attempting to read/update/delete.                                                                                                                                           |
| 429        | Too Many Requests     | The Rightsline API has daily and per-second limits. Retry the request after a 1 second delay. If error persists, you may have reached your daily limit.                                                         |
| 500        | Internal Server Error | Contact Rightsline Support.                                                                                                                                                                                     |
| 503        | Service Unavailable   | During UAT, you may receive this error when a new build is being deployed to one of the UAT environments. Simply retry the request after a few minutes.                                                         |
| 504        | Gateway Timeout       | If attempting to create/update record, try to retrieve the record. If record was not created/updated, retry the request. If attempting to retrieve temporary credentials or a record, simply retry the request. |
