---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - http
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the MakeShift API! 

# Authentication

> To authorize using a username and password, use this code:

```shell
curl --request POST \
  --url https://app.makeshift.ca/oauth/token \
  --header 'Cache-Control: no-cache' \
  --header 'Content-Type: application/json' \
  --data '{ "grant_type": "password", "username": "admin@appcolony.ca", "password": "appcolony" }'
```

```http
POST /oauth/token HTTP/1.1
Host: app.makeshift.ca
Content-Type: application/json
Cache-Control: no-cache

{
  "grant_type"  : "password",
  "username"    : "admin@appcolony.ca",
  "password"    : "appcolony"
}
```

> Make sure to replace your username and password information.

A MakeShift API token can be retrieved for any company admin using a username/password.

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer defaaddbb673c8afeef85666f07aa4a11f3e0a2f487bf9c714ab00ba2b11c614`

# Department/Shifts

## Get all shifts for a department

```http
GET /api/public/v1/departments/548/shifts?from=2018-01-01&to=2018-08-30 HTTP/1.1
Host: app.makehshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'http://localhost:3000/api/public/v1/departments/548/shifts?from=2018-01-01&to=2018-08-30' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": "135000",
      "type": "shift",
      "attributes": {
        "starts_at": "2018-07-27 07:00:00 -0700",
        "ends_at": "2018-07-27 13:00:00 -0700"
      },
      "relationships": {
        "user": {
          "data": {
            "id": "7422",
            "type": "user"
          }
        }
      }
    },
    {
      "id": "135001",
      "type": "shift",
      "attributes": {
        "starts_at": "2018-07-28 03:00:00 -0700",
        "ends_at": "2018-07-28 11:00:00 -0700"
      },
      "relationships": {
        "user": {
          "data": {
            "id": "7422",
            "type": "user"
          }
        }
      }
    }
  ]
}
```

This endpoint retrieves all shifts in a department, filtered by various optional parameters.

### HTTP Request

`GET /api/public/v1/departments/:id/shifts`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

