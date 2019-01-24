## Associate a user with a job site

This endpoint creates an association between a user and a job site.

### HTTP Request

`POST /api/public/v2/user_job_sites`

### Request Body

Parameter   | Required | Default | Description
---------   | -------- | ------- | -----------
user_id     | ✓        |         | User ID to associate with a job site
job_site_id | ✓        |         | Job Site ID to associate user with
