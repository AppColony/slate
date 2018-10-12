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
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` 
sort | None | Sorting parameters. Example: `?sort=-first_name,id`

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
external_id | `?filter[user][external_id]=G3XC900001` | A foreign key to identify users across systems
email | `?filter[user][email]=emailio.esteves@makeshift.ca` |
employee_id | `?filter[user][employee_id]=3030` |
role | `?filter[user][role]=department_admin` | Role should be one of `company_admin`, `location_admin`, `department_admin`, `employee`
updated_at | `?filter[user][updated_at](ge)=2018-10-03` | Find users that have been updated since a certain date (ISO8601 format)

### Pagination

User listings are paginated by default. The maximum number of users per page is 100. Without specifying any pagination parameters the endpoint will paginate the equivalent of "page 1, page size 100" like so:

`https://app.makeshift.ca/api/public/v1/users?page[number]=1&page[size]=100`

Different pages and smaller page sizes can be specified like so:

`https://app.makeshift.ca/api/public/v1/users?page[number]=3&page[size]=50`

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
