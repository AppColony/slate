## Get a Shift listing

```http
GET /api/public/v2/shifts HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/shifts' \
  -H 'Authorization: Bearer <token>'
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "133546",
      "type": "shift",
      "attributes": {
        "external_id": null,
        "department_id": 548,
        "user_id": 7347,
        "date": "2019-01-27",
        "starts_at": "2019-01-27 17:00:00 UTC",
        "ends_at": "2019-01-27 23:00:00 UTC",
        "time_zone": "America/Denver",
        "breaks": [],
        "notes": null,
        "published_at": "2016-06-16 17:07:40 UTC",
        "updated_at": "2018-10-24 21:48:11 UTC"
      },
      "relationships": {
        "position": {
          "data": {
            "id": "2835",
            "type": "position"
          }
        },
        "job_site": {
          "data": {
            "id": "6",
            "type": "job_site"
          }
        }
      }
    },
    {
    "id": "133547",
    "type": "shift",
    "attributes": {
      "external_id": null,
      "department_id": 548,
      "user_id": 7347,
      "date": "2019-01-29",
      "starts_at": "2019-01-29 14:00:00 UTC",
      "ends_at": "2019-01-29 21:30:00 UTC",
      "time_zone": "America/Denver",
      "breaks": [],
      "notes": null,
      "published_at": "2016-06-16 17:07:40 UTC",
      "updated_at": "2018-10-24 21:48:11 UTC"
      },
      "relationships": {}
    },
  ],
  "meta": {
      "shown": 100
  },
  "links": {
      "self": "/api/public/v2/shifts?page%5Bnumber%5D=1&page%5Bsize%5D=100",
      "next": "/api/public/v2/shifts?page%5Bnumber%5D=2&page%5Bsize%5D=100"
  }
}
```

Get a listing of Shifts for a company.

### HTTP Request

`GET /api/public/v2/shifts`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[shift]=starts_at,external_id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-first_name,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
id | `?filter[shift][id]=3471` | Shift ID
user_id | `?filter[shift][user_id]=7442` | User ID
external_id | `?filter[shift][external_id]=G3XC900001` | A foreign key to identify users across systems
department_id | `?filter[shift][department_id]=6789` | Department ID
location_id | `?filter[shift][location_id]=1234` | Location ID
date | `?filter[shift][date](eq)='2018-12-11'` | The start date of a shift (ISO8601 format)
starts_at | `?filter[shift][starts_at](ge)='2018-09-28 01:00:00 UTC'` | The start time of a Shift
ends_at | `?filter[shift][ends_at](ge)='2018-09-29 04:30:00 UTC'` | The end time of a Shift
updated_at | `?filter[shift][updated_at](ge)=2018-10-03` | Find Shifts that have been updated since a certain date (ISO8601 format)
published_at | `?filter[shift][updated_at](ge)=2018-10-03` | Find Shifts that have been pulished since a certain date (ISO8601 format)
published | `?filter[shift][updated_at](ge)=true` | Find Shifts that have been publshed

### Sortable Properties

Property | Example
-------- | -------
id | `shifts?sort=id`
user_id | `shifts?sort=updated_at`
department_id | `shifts?sort=department_id`
job_site_id | `shifts?sort=position_id`
position_id | `shifts?sort=position_id`
date | `shifts?sort=date`
starts_at | `shifts?sort=starts_at`
ends_at | `shifts?sort=ends_at`
update_at | `shifts?sort=updated_at`

Reference: <a href='#sorting'>Sorting</a>
