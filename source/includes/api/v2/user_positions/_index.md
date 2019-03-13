## Get a listing of user positions

```http
GET /api/public/v2/user_positions HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/user_positions' \
  -H 'Authorization: Bearer <token>'
```

```json
{
    "data": [
        {
            "id": "1",
            "type": "user_position",
            "attributes": {
                "user_id": 7421,
                "position_id": 1
            }
        }
    ],
    "meta": {
        "shown": 1
    },
    "links": {
    }
}
```


Get a listing of user positions for a company.

### HTTP Request

`GET /api/public/v2/user_positions`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[user_position]=id,user_id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-user_id,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
id | `?filter[user_position][id]=1` | User Positionn ID
position_id | `?filter[user_position][position_id]=1` | Position ID
user_id | `?filter[user_position][user_id]=1` | User ID

### Sortable Properties

Property | Example
-------- | -------
id | User Job Site ID
position_id | Position ID
user_id | User ID

Reference: <a href='#sorting'>Sorting</a>
