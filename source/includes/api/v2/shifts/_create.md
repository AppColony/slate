## Create a Shift

```http
POST /api/public/v2/users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "shift",
    "attributes": {
      "department_id": 551,
      "user_id": 7345,
      "starts_at": "2019-01-01T09:00-08",
      "ends_at": "2019-01-01T17:00-08"
    }
  }
}
```

```shell
curl --X POST 'http://localhost:3000/api/public/v2/shifts' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "shift",
    "attributes": {
      "department_id": 551,
      "user_id": 7345,
      "starts_at": "2019-01-01T09:00-08",
      "ends_at": "2019-01-01T17:00-08"
    }
  }
}'
```

> Error examples:

```json
{
  "errors": [
    {
      "title": "Conflict error",
      "detail": "Cannot create a shift on 2019-01-01 due to a conflict with Adam Millroy’s schedule.",
      "status": "400"
    }
  ]
}
```

This endpoint creates a new Shift. 

### HTTP Request

`POST /api/public/v2/shifts`

### Request Body

Parameter          | Required | Default     | Description
---------          | -------- | -------     | -----------
user_id            | ✓        |             | The ID of the User this Shift should be created in
department_id      | ✓        |             | The ID of the Department this Shift should be created in
starts_at          | ✓        |             | The start date/time of the Shift
ends_at            | ✓        |             | The end date/time of the Shift
external_id        | ✗        |             |
job_site_id        | ✗        |             |
notes              | ✗        |             |
position_id        | ✗        |             |
published          | ✗        |             | Set to `true` to have shift published immediately
breaks             | ✗        |             |

