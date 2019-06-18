## Update a User Position

```http
PUT /api/public/v2/users/7558/positions/2849 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

> A minimal payload example:

```json
{
  "data": {
    "type": "user_position",
    "attributes": {
      "wage": 10.85
    }
  }
}
```

```shell
curl -X PUT \
  https://app.makeshift.ca/api/public/v2/users/7558/positions/2849 \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
  -d '{
  "data": {
    "type": "user_position",
    "attributes": {
      "wage": 10.85
    }
  }
}'
```

You may update an existing User Position to add or remove a particular hourly wage associated with the given User in the given Position.

### HTTP Request

`PUT /api/public/v2/users/<user_id>/positions/<position_id>`

### Request Body

Parameter     | Description
---------     | -----------
wage          | Hourly wage for this User in this Position. Set to `null` to revert to the User's base wage when working in this Position. The value should be rounded to two decimal places. Example: `10.85`
