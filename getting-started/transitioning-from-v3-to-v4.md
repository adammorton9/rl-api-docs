---
description: Change notes for transitioning to using v4 of the Rightsline API.
---

# Transitioning from v3 to v4

### Adjust API URL and AWS region

The v4 Rightsline API is accessed using the subdomain <mark style="color:green;">**https://ris.rightsline.com**</mark>.

For access to other environments, please refer to [this table](../overview/#base-url-by-environment) for the proper v4 subdomain.

The AWS region for the US API has also been changed from us-east-1 to <mark style="color:green;">**us-west-2**</mark>. The EU region has not been changed (eu-central-1).

To transition to v4, adjust all existing calls' authorization to reference the new AWS region and update the URL of each endpoint to account for the new subdomain.

### Adjust calls to existing _Rightset_ endpoints to _Right_ endpoints

All **rightset** endpoints have been replaced by [**right** endpoints](../entities/right/) for consistency.

To transition to v4, adjust all existing calls to reference the new endpoint names.

### Update references to parentURL and childURL in calls to relationship endpoint to reference new objects

The parentUrl and childUrl properties have been removed from entity relationship objects, and have been replaced with parentTemplate, parentStatus, childTemplate, and childStatus objects.

To review what encompasses the entity relationship object, see [Relationship Object](../relationships/relationship-object.md).

{% tabs %}
{% tab title="v4" %}
{

&#x20;   "id": 255317359,&#x20;

&#x20;   "relationshipType": {&#x20;

&#x20;       "relationshipTypeId": 0,&#x20;

&#x20;       "relationshipTypeName": "Default"&#x20;

&#x20;   },&#x20;

&#x20;   "createdById": 1,&#x20;

&#x20;   "createdDate": "2019-10-30T20:54:23.297Z",&#x20;

&#x20;   "lastUpdatedById": 1,&#x20;

&#x20;   "lastUpdatedDate": "2019-10-30T20:54:23.297Z",&#x20;

&#x20;   "parentCharTypeId": 4,&#x20;

&#x20;   "parentRecordId": 1,&#x20;

&#x20;   <mark style="color:green;">"parentTemplate": {</mark>&#x20;

&#x20;       <mark style="color:green;">"templateId": 1,</mark>

&#x20;       <mark style="color:green;">"templateName": "Rights In"</mark>&#x20;

&#x20;   <mark style="color:green;">}</mark>,&#x20;

&#x20;   <mark style="color:green;">"parentStatus": {</mark>&#x20;

&#x20;       <mark style="color:green;">"statusId": 1,</mark>&#x20;

&#x20;       <mark style="color:green;">"statusName": "Active"</mark>&#x20;

&#x20;   <mark style="color:green;">}</mark>,&#x20;

&#x20;   "childCharTypeId": 1,&#x20;

&#x20;   "childRecordId": 1,&#x20;

&#x20;   <mark style="color:green;">"childTemplate": {</mark>&#x20;

&#x20;       <mark style="color:green;">"templateId": 1,</mark>&#x20;

&#x20;       <mark style="color:green;">"templateName": "Feature"</mark>&#x20;

&#x20;   <mark style="color:green;">}</mark>,&#x20;

&#x20;   <mark style="color:green;">"childStatus": {</mark>&#x20;

&#x20;       <mark style="color:green;">"statusId": 1,</mark>&#x20;

&#x20;       <mark style="color:green;">"statusName": "Active"</mark>&#x20;

&#x20;   <mark style="color:green;">}</mark>

}
{% endtab %}

{% tab title="v3" %}
{&#x20;

&#x20;   "id": 255317359,&#x20;

&#x20;   <mark style="color:red;">"parentURL": "https://api.rightsline.com/v3/deal/1"</mark>,&#x20;

&#x20;   <mark style="color:red;">"childURL": "https://api-staging.rightsline.com/v3/catalog-item/1"</mark>,&#x20;

&#x20;   "relationshipType": {&#x20;

&#x20;       "relationshipTypeId": 0,&#x20;

&#x20;       "relationshipTypeName": "Default"&#x20;

&#x20;   },&#x20;

&#x20;   "createdById": 1,&#x20;

&#x20;   "createdDate": "2019-10-30T20:54:23.297Z",&#x20;

&#x20;   "lastUpdatedById": 1,&#x20;

&#x20;   "lastUpdatedDate": "2019-10-30T20:54:23.297Z",&#x20;

&#x20;   "parentCharTypeId": 4,&#x20;

&#x20;   "parentRecordId": 1,&#x20;

&#x20;   "childCharTypeId": 1,&#x20;

&#x20;   "childRecordId": 1

}
{% endtab %}
{% endtabs %}

### Handle 403 - Forbidden response when unauthorized to update a field on an entity

If a user attempts to update fields on an entity that they do not have permission to update, the API will return a _403 - Forbidden_ status code, instead of ignoring that field in the request.

### Handle 403 - Forbidden response when unable to execute a workflow action from a status

If a user attempts to execute a workflow action on an entity where the action is not available from the current status, the API will now return a _403 - Forbidden_ status code with the message "Action X not available to be taken from status Y", instead of returning a _200 - OK_ status code with the message "false".

### Add statusUpdatedById and statusUpdatedDate fields on entity objects

Entity objects will now include two new fields, `statusUpdatedById` and `statusUpdatedDate`, indicating the user and time of the last status update.

To review what encompasses the entity object, see [Entity Object](../entities/the-entity-object.md).

{% tabs %}
{% tab title="v4" %}
{&#x20;

&#x20;   "relationshipUpdateRules": null,&#x20;

&#x20;   "id": 1,&#x20;

&#x20;   "revisionId": 0,&#x20;

&#x20;   "title": "The Three Stooges",&#x20;

&#x20;   "template": {&#x20;

&#x20;       "fields": \[],&#x20;

&#x20;       "templateId": 1,&#x20;

&#x20;       "templateName": "Collection",&#x20;

&#x20;       "processId": 0,&#x20;

&#x20;        "processName": null&#x20;

&#x20;   },&#x20;

&#x20;   "status": {&#x20;

&#x20;       "statusId": 1,&#x20;

&#x20;       "statusName": "Active"&#x20;

&#x20;   },&#x20;

&#x20;   "characteristics": {&#x20;

&#x20;       "release\_year": 1925&#x20;

&#x20;   },&#x20;

&#x20;   "comments": \[],&#x20;

&#x20;   "createdById": 1,&#x20;

&#x20;   "createdDate": "2015-08-25T21:07:02.487Z",&#x20;

&#x20;   "lastUpdatedById": 1,&#x20;

&#x20;   "lastUpdatedDate": "2020-05-02T02:17:13.717",&#x20;

&#x20;   <mark style="color:green;">"statusUpdatedById": 1</mark>,&#x20;

&#x20;  <mark style="color:green;">"statusUpdatedDate": "2020-05-02T02:17:13.717"</mark>&#x20;

}
{% endtab %}

{% tab title="v3" %}
{&#x20;

&#x20;   "relationshipUpdateRules": null,&#x20;

&#x20;   "id": 1,&#x20;

&#x20;   "revisionId": 0,&#x20;

&#x20;   "title": "The Three Stooges",&#x20;

&#x20;   "template": {&#x20;

&#x20;       "fields": \[],&#x20;

&#x20;       "templateId": 1,&#x20;

&#x20;       "templateName": "Collection",&#x20;

&#x20;       "processId": 0,&#x20;

&#x20;       "processName": null&#x20;

&#x20;   },&#x20;

&#x20;   "status": {&#x20;

&#x20;       "statusId": 1,&#x20;

&#x20;       "statusName": "Active"&#x20;

&#x20;   },&#x20;

&#x20;   "characteristics": {&#x20;

&#x20;       "release\_year": 1925&#x20;

&#x20;   },&#x20;

&#x20;   "comments": \[],&#x20;

&#x20;   "createdById": 1,&#x20;

&#x20;   "createdDate": "2015-08-25T21:07:02.487Z",&#x20;

&#x20;   "lastUpdatedById": 1,&#x20;

&#x20;   "lastUpdatedDate": "2020-05-02T02:17:13.717"&#x20;

}
{% endtab %}
{% endtabs %}

### Adjust all existing calls to search endpoints to return 100 records per page

Each search endpoint will return a max of 100 records per page.  If a value greater than 100 is passed in the `rows` field, the search will still only return 100 records per page.

To transition to v4, adjust all existing search calls to request a maximum of 100 rows.

### Adjust /\*-templates endpoint responses to no longer include fields, retrieve fields via /\*-templates/:id instead

To protect against the response size becoming too large, we have removed the `fields` from the `/*-templates` endpoint responses. To retrieve the fields on a template in v4, you will need to retrieve a specific template by its template ID, like `/v4/table-templates/2` will retrieve all the fields for table template ID 2. See [here](../config/templates.md#get-template-details) for an example.
