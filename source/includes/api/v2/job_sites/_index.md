## Get a listing of job sites

Get a listing of job sites for a company.

### HTTP Request

`GET /api/public/v2/job_sites`

### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
fields | All | A comma-separated list of fields to select. Example: `?fields[job_site]=name,id`
page | Page 1, Size 100 | Pagination parameters. Example: `?page[number]=1&page[size]=100` (Reference: <a href='#pagination'>Pagination</a>)
sort | None | Sorting parameters. Example: `?sort=-name,id` (Reference: <a href='#sorting'>Sorting</a>)

### Filterable Properties

Property | Example | Notes
-------- | ------- | -----
external_id | `?filter[job_site][external_name]=G3XC900001` | A foreign key to identify a job_site across systems
name | `?filter[job_site][name]=makeshift` | Job site name
department_id | `?filter[job_site][department_id]=makeshift` | Department ID

### Sortable Properties

Property | Example
-------- | -------
id | `job_site?sort=id`
department_id | `job_site?sort=department_id`
name | `job_site?sort=name`

Reference: <a href='#sorting'>Sorting</a>`