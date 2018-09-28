# Users

## Get a single user by ID

```http
GET /api/public/v1/users/7442 HTTP/1.1
Host: app.makeshift.ca
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
      "email": "shifty@makeshift.ca",
      "employee_id": "3030"
    }
  }
}
```

> Select only certain fields

```http
GET /api/public/v1/users/7442?fields[user]=first_name,email HTTP/1.1
Host: app.makeshift.ca
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

### Error Codes

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The kitten requested is hidden for administrators only.
404 | Not Found -- The specified kitten could not be found.
405 | Method Not Allowed -- You tried to access a kitten with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The kitten requested has been removed from our servers.
418 | I'm a teapot.
429 | Too Many Requests -- You're requesting too many kittens! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

## Get a user listing

```http
GET /api/public/v1/users HTTP/1.1
Host: app.makeshift.ca
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
        "email": "mallison+iadmin@appcolony.ca",
        "employee_id": "3030"
      }
    },
    {
      "id": "7345",
      "type": "user",
      "attributes": {
        "first_name": "Adam",
        "last_name": "Millroy",
        "email": "adammillroy7345@makeshift.ca",
        "employee_id": null
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


### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
email | `?filter[user][email]=emailio.esteves@makeshift.ca` |
employee_id | `?filter[user][employee_id]=3030` |
role | `?filter[user][role]=department_admin` | Role should be one of `company_admin`, `location_admin`, `department_admin`, `employee`

### Error Codes

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The kitten requested is hidden for administrators only.
404 | Not Found -- The specified kitten could not be found.
405 | Method Not Allowed -- You tried to access a kitten with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The kitten requested has been removed from our servers.
418 | I'm a teapot.
429 | Too Many Requests -- You're requesting too many kittens! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
