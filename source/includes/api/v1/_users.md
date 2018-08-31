# Users

## Get a single user by ID

```http
GET /api/public/v1/users/7442 HTTP/1.1
Host: app.makehshift.ca
Authorization: Bearer 6b215a11bae7a710c09e1040de3005039904afeaa381e05f4a587ac2613faf00
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v1/departments/548/shifts?from=2018-01-01&to=2018-08-30' \
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
      "email": "shifty@makeshift.ca"
    }
  }
}
```

This endpoint retrieves the data for a single user.

### HTTP Request

`GET /api/public/v1/users/<id>`

