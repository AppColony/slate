## Get a department listing

```http
GET /api/public/v2/departments HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/departments' \
  -H 'Authorization: Bearer <token>'
```

> The above command returns JSON structured like this:

```json
{
    "data": [
      {
        "id": "543",
        "type": "department",
        "attributes": {
          "name": "Kitchen",
          "location_id": 111,
          "external_id": "001",
          "api_id": "D-222",
          "last_published_at": "2019-01-29 23:51:09 UTC",
          "updated_at": "2019-01-29 23:51:09 UTC"
        },
        "relationships": {
          "users": {
              "data": [
                {
                  "id": "1111",
                  "type": "user"
                }
              ]
          },
          "positions": {
              "data": [
                {
                  "id": "3333",
                  "type": "position"
                }
              ]
          },
          "job_sites": {
            "data": [
              {
                "id": "4444",
                "type": "job_site"
              }
            ]
          }
        }
      }
  ],
  "meta": {
    "shown": 1
  },
  "links": {
    "self": "/api/public/v2/departments?page%5Bnumber%5D=1&page%5Bsize%5D=100"
  }
}
```

Get a listing of departments for a company.

### HTTP Request

`GET /api/public/v2/departments`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[department]=name,id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-name,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
api_id | `?filter[department][api_id]=G3XC900001` | A unique ID for identifying departments across systems
external_id | `?filter[department][external_name]=G3XC900001` | A department identifier
name | `?filter[department][name]=makeshift` | Department name
location_id | `?filter[department][location_id]=makeshift` | Location ID
updated_at | `?filter[department][updated_at](ge)=2018-10-03` | Find departments that have been updated since a certain date (ISO8601 format)

### Sortable Properties

Property | Example
-------- | -------
id | `departments?sort=id`
location_id | `departments?sort=location_id`
name | `departments?sort=name`

Reference: <a href='#sorting'>Sorting</a>
