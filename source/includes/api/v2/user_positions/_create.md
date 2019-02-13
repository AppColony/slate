## Associate a user with a position

```http
POST /api/public/v2/user_positions HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "user_position",
    "attributes": {
      "user_id": 7442,
      "position_id": 22
    }
  }
}
```

```shell
curl -X POST \
  https://app.makeshift.ca/api/public/v2/user_positions \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "user_position",
    "attributes": {
      "user_id": 7442,
      "position_id": 22
    }
  }
}'
```

This endpoint creates an association between a user and a position.

### HTTP Request

`POST /api/public/v2/user_positions`

### Request Body

Parameter   | Required | Default | Description
---------   | -------- | ------- | -----------
user_id     | ✓        |         | User ID to associate with a position
position_id | ✓        |         | Position ID to associate user with
