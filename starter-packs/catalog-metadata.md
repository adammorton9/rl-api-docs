# Catalog metadata



**GitHub Sample Application**

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



**Postman**

A collection of Postman calls are available to help you get started with interacting with the catalog-item Rightsline API.  A collection that can be imported into your workspace can be found @ [https://www.getpostman.com/collections/d4d84bd442a650819372](https://www.getpostman.com/collections/d4d84bd442a650819372)

There are example API calls for:

1. Getting temporary credentials
2. Searching the catalog
3. Creating a catalog item ( w/ a deal )
4. Updating a previous created catalog item
5. Retrieving a catalog item
6. Deleting a catalog item

#### Postman Environment Variables

<table><thead><tr><th width="150">Name</th><th>Descripion</th></tr></thead><tbody><tr><td>access_key</td><td>Follow the steps under <a href="../getting-started/#obtaining-api-credentials">Obtaining API Credentials</a> page to obtain your API key, access key, and secret keys.  These will be used to make calls into the Rightsline API.</td></tr><tr><td>secret_key</td><td>Follow the steps under <a href="../getting-started/#obtaining-api-credentials">Obtaining API Credentials</a> page to obtain your API key, access key, and secret keys.  These will be used to make calls into the Rightsline API.</td></tr><tr><td>endpoint_url</td><td>Determine the API endpoint ( see <a href="../overview/">Overview</a> page ) for your requests.</td></tr><tr><td>api_gateway</td><td>Follow the steps under <a href="../getting-started/#obtaining-api-credentials">Obtaining API Credentials</a> page to obtain your API key, access key, and secret keys.  These will be used to make calls into the Rightsline API.</td></tr><tr><td>version</td><td>This should be set to "v4" as that is the API version targeted by this documentation.</td></tr><tr><td>region</td><td>This should be set to "us-west-2" in order for the AWS authorization service to work.</td></tr><tr><td>catalog_id</td><td>This is an optional variable that can be used to define the catalog item </td></tr></tbody></table>

