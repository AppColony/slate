## Create a department

```http
POST /api/public/v2/departments HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "department",
    "attributes": {
      "name": "IT Dept.",
      "location_id": 222,
      "api_id": "D-222"
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca/api/public/v2/departments \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "department",
    "attributes": {
      "name": "IT Dept.",
      "location_id": 222,
      "api_id": "D-222"
    }
  }
}'
```

This endpoint creates a new department.

### HTTP Request

`POST /api/public/v2/departments`

### Request Body

Parameter          | Required | Default     | Description
---------          | -------- | -------     | -----------
name               | ✓        |             | Department's name
location_id        | ✓        |             | Location to which the Department belongs
external_id        | ✗        |             | An identifier for a Department
api_id             | ✗        |             | A unique ID for identifying a Department
