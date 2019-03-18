## Upsert a Location

```http
PATCH /api/public/v2/positions HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "location",
    "attributes": {
      "name": "Makeshift Fitness",
      "time_zone": "America/New_York",
      "api_id": "D-100"
    }
  }
}
```

```shell
curl -X PATCH \
  https://app.makeshift.ca/api/public/v2/positions \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "location",
    "attributes": {
      "name": "Makeshift Fitness",
      "time_zone": "America/New_York",
      "api_id": "D-100"
    }
  }
}'
```

This endpoint will update a Location with a given API ID, or create one if it doesn't exist.

### HTTP Request

`PATCH /api/public/v2/locations`

### Request Body

Parameter          |  Create   | Update       | Description
---------          | --------- | ----------   |-----------
api_id             |  ✓        | ✓            | A unique idenfier for a Location
name               |  ✓        | ○            | Location's name
time_zone          |  ✓        | ✗            | Location's time zone
week_starts_on     |  ○        | ✗            | A value from 0 to 6 indicating which day of the week the calendar

✓ = Required &nbsp; ○ = Optional &nbsp; ✗ = Ignored

