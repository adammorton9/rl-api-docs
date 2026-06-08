# Limitations

* Batch requests are limited to 100 records per batch.  Each batch request will only count as 1 request for the purposes of API call limits, regardless of the number of records in the batch.
* We allow a maximum of 10 batches in a queued or processing state per client.  If you try to submit an additional batch during this time, you will receive a 429 response code. See[ API request limits ](../../overview/request-limits.md)for more information.
* A batch request is limited to one of the following batch methods for the entire request.
