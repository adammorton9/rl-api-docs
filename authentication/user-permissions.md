# User permissions

### User Activity and Data Policies

The actions that a user is allowed to take and the data they are able to retrieve via the Rightsline API are determined by the permissions granted to them by the Activity and Data Policies that are assigned to them.  The same actions and data that are available through the Rightsline application for a user are available when calling the API.

{% hint style="info" %}
A read-only user will be able to access endpoints via the GET method to retrieve records and relationships, but will not be able to create or update records via the POST and PUT methods.  Read-only users would also have permission to POST to the /search endpoints to retrieve records and relationships.&#x20;
{% endhint %}
