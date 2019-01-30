## Associate a user with a position

This endpoint creates an association between a user and a position.

### HTTP Request

`POST /api/public/v2/user_positions`

### Request Body

Parameter   | Required | Default | Description
---------   | -------- | ------- | -----------
user_id     | ✓        |         | User ID to associate with a position
position_id | ✓        |         | Position ID to associate user with
