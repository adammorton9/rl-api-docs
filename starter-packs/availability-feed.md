# Availability feed

Rightsline Availability Endpoints and Message Queues may be used to validate Content availability for integrated scheduling, sales, and publishing processes. Some sample scenarios include:&#x20;

Content Scheduling for Linear and Non-Linear Distribution - As Content Rights are finalized, the message queue may alert an integration to synchronize Availability Windows to your scheduling systems. Additionally, as Availability is updated due to new Sales, Holdbacks, or Restrictions, the message queue will send a message that Content Availability has been updated, alerting an integration to call and synchronize the latest Availability Windows to your scheduling System.

Content Use Validation for Sales and Publishing - As Sales and Publishing Teams working in connected systems identify Library Content that may be used for new opportunities, an integration may call to the Rightsline Availability Endpoint and determine whether Content is cleared for use. Rightsline Availability Endpoints may return either a simple True or False response, or a more detailed response including Availability Window Dates and a response as to why Content may be partially available or unavailable.



A sample application showing how to listen for and process AWS SNS messages via an AWS Lambda function is available on GitHub ( [https://github.com/rightsline/sample-lambda](https://github.com/rightsline/sample-lambda) ).

To use the sample application you will need to perform the following steps:

1.  The nomenclature for SNS topics is as follows:

    `{environment}-rtl-div{div_number}-v4-ct{char_type_id}`

    * **environment**: See table "Environment Variable" below.
    * **div**: this is your company identifier assigned by Rightsline, typically a two to four digit number
    * **char\_type\_id**: See char type table at [Char types](../entities/char-types.md)
2. Provide your **Rightsline representative** with your AWS account id along with the SNS topics you wish to subscribe.  They will set up the required access policies so you can begin receiving messages.
3. Follow the steps under [Obtaining API Credentials](../getting-started/#obtaining-api-credentials) page to obtain your API key, access key, and secret keys.  These will be used to make calls into the Rightsline API.
4. Determine the API endpoint ( see [Overview](../overview/) page ) for your requests.

#### Environment Variable

| Environment | `{environment} Value` |
| ----------- | --------------------- |
| Production  | prd                   |
| Integration | int                   |
| Staging     | stg                   |



When executing your lambda you will need to set the following inputs to the function:

* **RLAPIKEY**: This is provided to your company by Rightsline ( contact Rightsline representative ).
* **RLACCESSKEY:** This is created in step 3 above and tied to your Rightsline user account.
* **RLSECRETKEY**: This is created in step 3 above and tied to your Rightsline user account.
* **RLAPIURL**: This is found in step 4 above (no protocol needed, just the hostname - api.rightsline.com).

