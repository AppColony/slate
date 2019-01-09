## Create a department

This endpoint creates a new department.

### HTTP Request

`POST /api/public/v2/departments`

### Request Body

Parameter          | Required | Default     | Description
---------          | -------- | -------     | -----------
name               | ✓        |             | Department's name
location_id        | ✓        |             | Location to which the Department belongs
external_id        | ✗        |             | An ID by which an API wishes to identify a Department
