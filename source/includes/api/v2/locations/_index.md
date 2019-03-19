## Get a Location listing

```http
GET /api/public/v2/locations HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/locations' \
  -H 'Authorization: Bearer <token>'
```

```json
{
  "data": [
    {
      "id": "222",
      "type": "location",
      "attributes": {
          "name": "Victoria",
          "time_zone": "America/Los_Angeles",
          "external_name": null,
          "api_id": null,
          "week_starts_on": 0
      },
      "relationships": {
        "departments": {
          "data": [
            {
              "id": "1",
              "type": "department"
            }
          ]
        }
      }
    },
    {
      "id": "333",
      "type": "location",
      "attributes": {
        "name": "Calgary",
        "time_zone": "America/Denver",
        "external_name": null,
        "api_id": null,
        "week_starts_on": 0
      },
      "relationships": {
        "departments": {
          "data": [
            {
              "id": "555",
              "type": "department"
            },
          ]
        }
      }
    }
  ],
  "meta": {
      "shown": 2
  },
  "links": {
      "self": "/api/public/v2/locations?page%5Bnumber%5D=1&page%5Bsize%5D=100"
  }
}
```

Get a listing of Locations for a company.

### HTTP Request

`GET /api/public/v2/locations`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[location]=name,id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-name,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
api_id | `?filter[location][api_id]=L-700` | A foreign key to identify Locations across systems
external_name | `?filter[location][external_name]=G3XC900001` | An identifier for a Location
name | `?filter[location][name]=makeshift` | Location name
updated_at | `?filter[location][updated_at](ge)=2018-10-03` | Find Locations that have been updated since a certain date (ISO8601 format)

### Sortable Properties

Property | Example
-------- | -------
id | `locations?sort=id`
name | `locations?sort=name`

Reference: <a href='#sorting'>Sorting</a>
