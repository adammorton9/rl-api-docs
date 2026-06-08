---
description: The new features and endpoints available as part of v4 of the Rightsline API.
---

# 🆕 What's new in v4?

### :star2:[Bulk requests](../batch/create.md)

Bulk requests are now available!:tada:&#x20;

You are now able to retrieve, create, modify, and delete up to 100 records/relationships with a single API request.  You are also able to execute workflow actions on up to 100 records with a single request.  Simply [create a batch request](../batch/create.md) with the desired record IDs, and then [retrieve the batch](../batch/retrieve.md) to return the requested records.

### :rewind: [Audit History](../entities/deal/audit-history.md#get-deal-audit-history)

We have added the ability to retrieve audit history for any record in Rightsline, as well as get specific details about what value was changed for each audit history entry.

### :currency\_exchange:[Currency conversion](../config/currency-conversion-sept-16/)&#x20;

It is now possible to [create](../config/currency-conversion-sept-16/currency-conversion-create.md), [read](../config/currency-conversion-sept-16/currency-conversion-retrieve.md), [update](../config/currency-conversion-sept-16/currency-conversion-update.md), and [delete ](../config/currency-conversion-sept-16/currency-conversion-delete.md)currency conversion configurations via the API. &#x20;

### :frame\_photo:[Key art](../entities/catalog-item/update-catalog-item-key-art.md)

You are now able to [update](../entities/catalog-item/update-catalog-item-key-art.md) and [delete ](../entities/catalog-item/delete-catalog-item-key-art.md)the key art for [catalog](../entities/catalog-item/update-catalog-item-key-art.md) and [inventory](../entities/inventory/update-an-inventory-key-art.md) records.

### :information\_source:[Additional template endpoints](../entities/catalog-item/retrieve-catalog-item-draft-templates.md)

We have added additional endpoints to be able to retrieve more information about template configuration. &#x20;

* [**Draft templates**](../entities/catalog-item/retrieve-catalog-item-draft-templates.md) - Retrieve draft templates for an entity. The draft template IDs in the response can be used to execute workflow actions that create a document (see [below](whats-new-in-v4.md#execute-document-workflow-action)).
* [ **Retrieve a specific template by ID**](../config/templates.md) - In addition to retrieving all configuration templates for a given char type, you can now specify the ID of a specific template to retrieve even more details, such as parent and child related templates, and any associated parties.
* [**Retrieve a specific field on a template**](../config/templates.md) - You are also now able to retrieve details about a specific characteristic on a template.

### :toolbox:[Execute document workflow action](../workflow/execute-document-workflow-action.md)

Execute workflow actions that create a document using our new execute document workflow action endpoints.

### :arrow\_up:[Upload files larger than 10mb](../entities/file/file-create.md)

In v4 of the Rightsline API, we now allow larger file uploads exceeding the previous 10mb limit.  See an example of how to upload a file [here](../entities/file/file-create.md#example-upload-a-file).

### 🔠[Add/remove pick list values](../config/lists/)

Add or remove values from master value lists and pick lists.
