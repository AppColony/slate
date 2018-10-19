## Get a user by ID

```http
GET /api/public/v2/users/7442 HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/users/7442' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": "7442",
    "type": "user",
    "attributes": {
      "first_name": "Shifty",
      "last_name": "McGee",
      "email": "shifty@makeshift.ca",
      "employee_id": "3030",
      "role": "employee"
    }
  }
}
```

> Select only certain fields

```http
GET /api/public/v2/users/7442?fields[user]=first_name,email HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/users/7442?fields[user]=first_name,email' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b' \
```

```json
{
  "data": {
    "id": "7442",
    "type": "user",
    "attributes": {
      "first_name": "Shifty",
      "email": "shifty@makeshift.ca"
    }
  }
}
```

This endpoint retrieves the data for a single user.

### HTTP Request

`GET /api/public/v2/users/<id>`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[user]=first_name,email`
