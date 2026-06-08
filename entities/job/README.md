# Job

### Endpoints

| Method | Endpoint                     | Description                                                      |
| ------ | ---------------------------- | ---------------------------------------------------------------- |
| POST   | /v4/job                      | [Create a job.](job-create.md)                                   |
| GET    | /v4/job/:id                  | [Retrieve a job.](job-retrieve.md)                               |
| PUT    | /v4/job/:id                  | [Update a job.](job-update.md)                                   |
| DELETE | /v4/job/:id                  | [Delete a job.](job-delete.md)                                   |
| GET    | /v4/job-templates            | [Retrieve job templates.](../../config/templates.md)             |
| GET    | /v4/job-statuses/:templateId | [Retrieve job statuses.](retrieve-job-statuses.md)               |
| GET    | /v4/job/:id/draft-templates  | [Retrieve job draft templates.](retrieve-job-draft-templates.md) |
| POST   | /v4/job/:id/switch-template  | [Switch job template.](switch-job-template.md)                   |
