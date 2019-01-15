## Associate a user with a department

This endpoint creates an association between a user and a department.

### HTTP Request

`POST /api/public/v2/department_users`

### Request Body

Parameter     | Required | Default | Description
---------     | -------- | ------- | -----------
user_id       | ✓        |         | User ID to associate to a department
department_id | ✓        |         | Department ID to associate user with
