## Get a DeletedShift listing

```http
GET /api/public/v2/deleted_shifts HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer <token>
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/deleted_shifts' \
  -H 'Authorization: Bearer <token>'
```

> The above command returns JSON structured like this:

```json
```

Get a listing of deleted Shifts for a company.

### HTTP Request

`GET /api/public/v2/deleted_shifts`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[deleted_shift]=starts_at,ends_at`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=created_at` (Reference: <a href='#sorting'>Sorting</a>)


