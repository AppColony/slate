## Get a listing of User Job Sites

```http
GET /api/public/v2/user_job_sites HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/user_job_sites' \
  -H 'Authorization: Bearer <token>'
```

```json
{
    "data": [
        {
            "id": "1",
            "type": "user_job_site",
            "attributes": {
                "user_id": 7421,
                "job_site_id": 1
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


Get a listing of User Job Sites for a company.

### HTTP Request

`GET /api/public/v2/user_job_sites`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[user_job_site]=id,user_id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-user_id,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
id | `?filter[user_job_site][id]=1` | User Job Site ID
job_site_id | `?filter[user_job_site][job_site_id]=1` | Job Site ID
user_id | `?filter[user_job_site][user_id]=1` | User ID

### Sortable Properties

Property | Example
-------- | -------
id | User Job Site ID
job_site_id | Job Site ID
user_id | User ID

Reference: <a href='#sorting'>Sorting</a>
