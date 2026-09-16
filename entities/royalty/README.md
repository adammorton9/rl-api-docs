# Royalty

Char Type ID: **13**

{% hint style="info" %}
For a step-by-step guide on creating royalty sets, associating them to deals and catalog items, creating royalty splits, and associating contacts, see Financial > Create a royalty.
{% endhint %}

### Endpoints

| Method | Endpoint                          | Description                          |
| ------ | --------------------------------- | ------------------------------------ |
| POST   | /v4/royalty                       | Create a royalty.                    |
| GET    | /v4/royalty/:id                   | Retrieve a royalty.                  |
| PUT    | /v4/royalty/:id                   | Update a royalty.                    |
| DELETE | /v4/royalty/:id                   | Delete a royalty.                    |
| GET    | /v4/royalty-templates             | Retrieve royalty templates.          |
| GET    | /v4/royalty-statuses/:templateId  | Retrieve royalty statuses.           |
| GET    | /v4/royalty-processes             | Retrieve royalty workflow processes. |
| GET    | /v4/royalty/:id/draft-templates   | Retrieve royalty draft templates.    |
| GET    | /v4/royalty/:id/audit-history     | Retrieve royalty audit history.      |
| POST   | /v4/royalty/:id/switch-template   | Switch royalty template.             |
| GET    | /v4/royalty/:id/validation-errors | Retrieve royalty validation errors.  |
