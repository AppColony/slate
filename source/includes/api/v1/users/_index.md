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

## Get a user by email

```http
GET /api/public/v1/users HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v1/users?filter[user][email]=adammillroy7345@makeshift.ca' \
  -H 'Authorization: Bearer <token>'
```

> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "id": "7345",
            "type": "user",
            "attributes": {
                "external_id": null,
                "first_name": "Adam",
                "last_name": "Millroy",
                "email": "adammillroy7345@makeshift.ca",
                "employee_id": "1071",
                "updated_at": "2016-08-09 20:11:46 UTC"
            }
        }
    ]
}
```

You may use a filter to retrieve users matching specific criteria. In this case, we use a filter by email address to find users who have that specific email.

To filter by a specific attribute, append a `filter` clause to the query string. `filter` clauses may be composed together if you would like to find users meeting a set of criteria.