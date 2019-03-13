## Get a listing of positions

```http
GET /api/public/v2/positions HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/positions' \
  -H 'Authorization: Bearer <token>'
```

```json
{
    "data": [
        {
            "id": "2888",
            "type": "position",
            "attributes": {
                "department_id": 548,
                "name": "Chef",
                "external_name": null,
                "api_id": null
            }
        }
    ],
    "meta": {
        "shown": 1
    },
    "links": {
        "self": "/api/public/v2/positions?page%5Bnumber%5D=1&page%5Bsize%5D=100"
    }
}
```

Get a listing of positions for a company.

### HTTP Request

`GET /api/public/v2/positions`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[position]=name,id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-name,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
api_id   | `?filter[position][api_id]=P-202` | A unique ID for identifying a position across systems
external_name | `?filter[position][external_name]=G3XC900001` | An indentifier for a position
name | `?filter[position][name]=makeshift` | Position name
department_id | `?filter[position][department_id]=makeshift` | Department ID

### Sortable Properties

Property | Example
-------- | -------
id | `positions?sort=id`
department_id | `positions?sort=department_id`
name | `positions?sort=name`

Reference: <a href='#sorting'>Sorting</a>
