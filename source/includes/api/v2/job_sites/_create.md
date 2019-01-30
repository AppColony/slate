## Create a job site

This endpoint creates a new job site.

### HTTP Request

`POST /api/public/v2/job_sites`

### Request Body

Parameter          | Required | Default     | Description
---------          | -------- | -------     | -----------
name               | ✓        |             | Job Site's name
department_id      | ✓        |             | Department to which the Job Site belongs
external_id        | ✗        |             | An ID by which an API wishes to identify a Job Site
