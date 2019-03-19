## Get a listing of Job Sites

```http
GET /api/public/v2/job_sites HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/job_sites' \
  -H 'Authorization: Bearer <token>'
```

```json
{
    "data": [
        {
            "id": "1",
            "type": "job_site",
            "attributes": {
                "department_id": 548,
                "name": "Job Site 0001",
                "external_id": null,
                "api_id": "J-200"
            }
        }
    ],
    "meta": {
        "shown": 1
    },
    "links": {
    }
}
```


Get a listing of Job Sites for a company.

### HTTP Request

`GET /api/public/v2/job_sites`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[job_site]=name,id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-name,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
api_id   | `?filter[job_site][api_id]=J-200` | A unique ID for identifying a Job Site.
external_id | `?filter[job_site][external_name]=G3XC900001` | An identifier for a Job Site.
name | `?filter[job_site][name]=makeshift` | Job Site name
department_id | `?filter[job_site][department_id]=makeshift` | Department ID

### Sortable Properties

Property | Example
-------- | -------
id | `job_site?sort=id`
department_id | `job_site?sort=department_id`
name | `job_site?sort=name`

Reference: <a href='#sorting'>Sorting</a>
