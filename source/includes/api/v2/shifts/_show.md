## Get a shift by ID

```http
GET /api/public/v2/shifts/135000 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/shifts/135000' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "id": "135000",
        "type": "shift",
        "attributes": {
            "external_id": null,
            "department_id": 548,
            "user_id": 7422,
            "date": "2019-01-04",
            "starts_at": "2019-01-04 16:00:00 UTC",
            "ends_at": "2019-01-05 00:00:00 UTC",
            "time_zone": "America/Denver",
            "breaks": [],
            "notes": null,
            "published_at": "2016-06-16 17:07:41 UTC",
            "updated_at": "2018-10-24 21:48:11 UTC"
        },
        "relationships": {
            "position": {
                "data": {
                    "id": "2851",
                    "type": "position"
                }
            },
            "job_site": {
                "data": {
                    "id": "2851",
                    "type": "job_site"
                }
            }
        }
    }
}
```

> Select only certain fields

```http
GET /api/public/v2/shifts/135000?fields[shift]=starts_at,external_id HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/shifts/135000?fields[shift]=starts_at,external_id' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
```

```json
{
  "data": {
    "id": "135000",
    "type": "shift",
    "attributes": {
      "external_id": null,
      "starts_at": "2019-01-04 16:00:00 UTC",
    }
  }
}
```

This endpoint retrieves the data for a single shift.

### HTTP Request

`GET /api/public/v2/shifts/<id>`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[shift]=starts_at,user_id`
