## Create a Position

```http
POST /api/public/v2/positions HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "position",
    "attributes": {
      "name": "Chef",
      "department_id": 548
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca/api/public/v2/positions \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "position",
    "attributes": {
      "name": "Chef",
      "department_id": 548
    }
  }
}'
```

This endpoint creates a new Position.

### HTTP Request

`POST /api/public/v2/positions`

### Request Body

Parameter     | Required | Default | Description
---------     | -------- | ------- | -----------
name          | ✓        |         | Position's name
department_id | ✓        |         | Department to which the Position belongs
api_id        | ✗        |         | A unique ID for identifying a Position.
external_name | ✗        |         | An identifier for a Position.
