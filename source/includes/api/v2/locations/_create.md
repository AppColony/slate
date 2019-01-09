## Create a location

This endpoint creates a new location.

### HTTP Request

`POST /api/public/v2/locations`

### Request Body

Parameter      | Required | Default | Description
---------      | -------- | ------- | -----------
name           | ✓        |         | Location's name
time_zone      | ✓        |         | Time zone string for the location (e.g. "America/New_York")
external_name  | ✗        |         | An ID by which an API wishes to identify a Location
week_starts_on | ✗        | 0       | A value from 0 to 6 indicating which day of the week the calendar should start on. 0 = Sunday, 1 = Monday, ..., 6 = Saturday
