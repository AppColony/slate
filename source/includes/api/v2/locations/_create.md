## Create a location

```http
POST /api/public/v2/locations HTTP/1.1
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
      "time_zone": "America/New_York"
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca/api/public/v2/locations \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "location",
    "attributes": {
      "name": "Makeshift Fitness",
      "time_zone": "America/New_York"
    }
  }
}'
```

This endpoint creates a new location.

### HTTP Request

`POST /api/public/v2/locations`

### Request Body

Parameter      | Required | Default | Description
---------      | -------- | ------- | -----------
name           | ✓        |         | Location's name
time_zone      | ✓        |         | Time zone string for the location (e.g. "America/New_York")
external_name  | ✗        |         | An ID by which an API wishes to identify a Location
week_starts_on | ✗        | 0       | A value from 0 to 6 indicating which day of the week the calendar should start on. 0 = Sunday, 1 = Monday, ..., 6 = Saturday
