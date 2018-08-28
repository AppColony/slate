# Department/Shifts

## Get all shifts for a department

```http
GET /api/public/v1/departments/548/shifts?from=2018-01-01&to=2018-08-30 HTTP/1.1
Host: app.makehshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v1/departments/548/shifts?from=2018-01-01&to=2018-08-30' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "135000",
      "type": "shift",
      "attributes": {
        "starts_at": "2018-07-27 07:00:00 -0700",
        "ends_at": "2018-07-27 13:00:00 -0700"
      },
      "relationships": {
        "user": {
          "data": {
            "id": "7422",
            "type": "user"
          }
        }
      }
    },
    {
      "id": "135001",
      "type": "shift",
      "attributes": {
        "starts_at": "2018-07-28 03:00:00 -0700",
        "ends_at": "2018-07-28 11:00:00 -0700"
      },
      "relationships": {
        "user": {
          "data": {
            "id": "7422",
            "type": "user"
          }
        }
      }
    }
  ]
}
```

This endpoint retrieves all shifts in a department, filtered by various optional parameters.

### HTTP Request

`GET /api/public/v1/departments/:id/shifts`

### Query Parameters

Parameter | Description | Type
--------- | ------- | -----------
from | Start of date range filter | ISO8601 Date String (Ex: "2018-11-23")
to | End of date range filter | ISO8601 Date String (Ex: "2018-11-23")

