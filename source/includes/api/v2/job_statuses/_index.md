## Get a listing of Job Statuses

```http
GET /api/public/v2/job_statuses HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  https://app.makeshit.ca/api/public/v2/job_statuses \
  -H 'Authorization: Bearer <token>' \
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "830324a3dd44a2d339bdc6af1b04412b",
      "type": "job_status",
      "attributes": {
        "job_name": "user_archive",
        "state": "running"
      }
    },
    {
      "id": "d85a36cce4c7b4964413d056d8da7b39",
      "type": "job_status",
      "attributes": {
        "job_name": "user_archive",
        "state": "completed"
      }
    }
  ],
  "meta": {
    "shown": 2
  },
  "links": {
    "self": "https://app.makeshift.ca/api/public/v2/job_statuses?page%5Bnumber%5D=1&page%5Bsize%5D=100"
  }
}
```

TODO: Description

### HTTP Request

`GET /api/public/v2/job_statuses`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[job_status]=state`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=created_at` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
api_id | `?filter[job_status][state]=running` | The state of the job (queued, running, completed, failed)
created_at | `?filter[job_status][created_at](ge)=2018-10-03` | Find jobs that have been created since a certain date/time (ISO8601 format)

### Sortable Properties

Property | Example
-------- | -------
created_at | `users?sort=created_at`

Reference: <a href='#sorting'>Sorting</a>
