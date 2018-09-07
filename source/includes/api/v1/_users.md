# Users

## Get a single user by ID

```http
GET /api/public/v1/users/7442 HTTP/1.1
Host: app.makehshift.ca
Authorization: Bearer 6b215a11bae7a710c09e1040de3005039904afeaa381e05f4a587ac2613faf00
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v1/users/7442' \
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

> Select only certain fields 

```http
GET /api/public/v1/users/7442?fields[user]=first_name,email HTTP/1.1
Host: app.makehshift.ca
Authorization: Bearer 354c1536272216645a6a9f60670f69d302228f6277de100221799f4508f1db95
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v1/users/7442?fields[user]=first_name,email' \
  -H 'Authorization: Bearer 354c1536272216645a6a9f60670f69d302228f6277de100221799f4508f1db95' \
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

`GET /api/public/v1/users/<id>`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[user]=first_name,email`


## Get a user listing

```http
GET /api/public/v1/users HTTP/1.1
Host: app.makehshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v1/users' \
  -H 'Authorization: Bearer <token>'
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "7344",
      "type": "user",
      "attributes": {
        "first_name": "Company",
        "last_name": "Admin",
        "email": "mallison+iadmin@appcolony.ca"
      }
    },
    {
      "id": "7345",
      "type": "user",
      "attributes": {
        "first_name": "Adam",
        "last_name": "Millroy",
        "email": "adammillroy7345@makeshift.ca"
      }
    }
  ],
  "meta": {
    "total": 2
  }
}
```

Get a listing of users for a company.

### HTTP Request

`GET /api/public/v1/users`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[user]=first_name,email`
