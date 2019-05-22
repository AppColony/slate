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

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
date | `?filter[deleted_shift][date](eq)='2018-12-11'` | The start date of a Shift (ISO8601 format)
deleted_at | `?filter[deleted_shift][deleted_at](ge)='2019-06-01 00:00:00 UTC'` | The time the Shift was deleted
department_id | `?filter[deleted_shift][department_id]=6789` | Department ID
ends_at | `?filter[deleted_shift][ends_at](ge)='2018-09-29 04:30:00 UTC'` | The end time of a Shift
published | `?filter[deleted_shift][updated_at](ge)=true` | Find Shifts that have been publshed
published_at | `?filter[deleted_shift][updated_at](ge)=2018-10-03` | Find Shifts that have been pulished since a certain date (ISO8601 format)
shift_id | `?filter[deleted_shift][shift_id]=17001` | The original (deleted) Shift ID
starts_at | `?filter[deleted_shift][starts_at](ge)='2018-09-28 01:00:00 UTC'` | The start time of a Shift
updated_at | `?filter[deleted_shift][updated_at](ge)=2018-10-03` | Find Shifts that have been updated since a certain date (ISO8601 format)
user_id | `?filter[deleted_shift][user_id]=7442` | User ID

### Sortable Properties

Property | Example
-------- | -------
user_id | `deleted_shifts?sort=updated_at`
department_id | `deleted_shifts?sort=department_id`
job_site_id | `deleted_shifts?sort=position_id`
position_id | `deleted_shifts?sort=position_id`
date | `deleted_shifts?sort=date`
starts_at | `deleted_shifts?sort=starts_at`
ends_at | `deleted_shifts?sort=ends_at`
updated_at | `deleted_shifts?sort=updated_at`

Reference: <a href='#sorting'>Sorting</a>


