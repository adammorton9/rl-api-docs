# Inventory

### Endpoints

| Method | Endpoint                           | Description                                                                  |
| ------ | ---------------------------------- | ---------------------------------------------------------------------------- |
| POST   | /v4/inventory                      | [Create an inventory item.](inventory-create.md)                             |
| GET    | /v4/inventory/:id                  | [Retrieve an inventory item.](inventory-retrieve.md)                         |
| PUT    | /v4/inventory/:id                  | [Update an inventory item.](inventory-update-1.md)                           |
| DELETE | /v4/inventory/:id                  | [Delete an inventory item.](inventory-delete.md)                             |
| GET    | /v4/inventory-templates            | [Retrieve inventory templates.](../../config/templates.md)                   |
| GET    | /v4/inventory-statuses/:templateId | [Retrieve inventory statuses.](retrieve-inventory-statuses.md)               |
| GET    | /v4/inventory/:id/draft-templates  | [Retrieve inventory draft templates.](retrieve-inventory-draft-templates.md) |
| GET    | /v4/inventory/:id/keyart/url       | [Retrieve an inventory key art URL.](retrieve-an-inventory-key-art-url.md)   |
| PUT    | /v4/inventory/:id/keyart           | [Update an inventory key art.](update-an-inventory-key-art.md)               |
| DELETE | /v4/inventory/:id/keyart           | [Delete an inventory key art.](delete-an-inventory-key-art.md)               |
| POST   | /v4/inventory/:id/switch-template  | [Switch inventory template.](switch-inventory-template.md)                   |

