---
description: >-
  Quickly create multiple records based on an existing series of records per
  char type.
---

# Data default, aka Profiles

In the UI, primarily UX2, these are known as profiles and you may see a list of "Table Profiles" or "Right Profiles".\
Data defaults allow you to save a series of records (tables and rights) and re-create them within a different module (deal, catalog,etc.).

### Data Default Endpoints

<table data-header-hidden><thead><tr><th width="162">Method</th><th width="375">Endpoint</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>Method name</td><td>Endpoint</td><td>Description</td><td>dnE</td></tr><tr><td><code>GET</code></td><td>/v4/:charType/:id/data-default</td><td>Retrieve data default list based on char type and </td><td></td></tr><tr><td><code>POST</code></td><td>/v4/:charType/data-default</td><td>Create a data default set for the specified char type.</td><td></td></tr><tr><td><code>POST</code></td><td>/v4/:charType/:id/data-default</td><td>Apply a Data Default to the specified id.</td><td></td></tr><tr><td><code>DELETE</code></td><td>/v4/:charType/data-default/:dataDefaultGuid</td><td>Delete the specified data default based on the GUID.</td><td></td></tr></tbody></table>
