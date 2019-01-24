## Create a position

This endpoint creates a new position.

### HTTP Request

`POST /api/public/v2/positions`

### Request Body

Parameter     | Required | Default | Description
---------     | -------- | ------- | -----------
name          | ✓        |         | Position's name
department_id | ✓        |         | Department to which the Position belongs
external_name | ✗        |         | An ID by which an API wishes to identify a Position
