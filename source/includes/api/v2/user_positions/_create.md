## Associate a User with a Position

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
      "position_id": 22,
      "wage": 15.25
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
      "position_id": 22,
      "wage": 15.25
    }
  }
}'
```

This endpoint creates an association between a User and a Position.

### HTTP Request

`POST /api/public/v2/user_positions`

### Request Body

Parameter   | Required | Default | Description
---------   | -------- | ------- | -----------
user_id     | ✓        |         | User ID to associate with a Position
position_id | ✓        |         | Position ID to associate with a User
wage        |          | `null`  | Optional wage for this User in this Position. Default of `null` will use the User's base hourly wage when they are working in this Position. The value should be rounded to two decimal places. Example: `10.85`
