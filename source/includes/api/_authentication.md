# Authentication

> To authorize using a key and secret, use this code:

```http
POST /oauth/token HTTP/1.1
Host: id.makeshift.ca
Content-Type: application/json
Cache-Control: no-cache

{
  "grant_type"  : "password",
  "username"    : "<key>",
  "password"    : "<secret>"
}
```

```shell
curl --request POST \
  --url https://id.makeshift.ca/oauth/token \
  --header 'Cache-Control: no-cache' \
  --header 'Content-Type: application/json' \
  --data '{ "grant_type": "password", "username": "<key>", "password": "<secret>" }'
```

> Response example:

```json
{
    "access_token": "c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b",
    "token_type": "bearer",
    "created_at": 1538759368,
    "user": {
        "id": 7443,
        "name": "api",
        "role": "company_admin",
        "email": "1d96d6787ce94e2af870d68d795d0201",
        "employee_id": "1d96d6787ce94e2af870d68d795d0201",
        "company_id": 269
    }
}
```

> To use your token in API requests:

```http
GET /api/public/v2/<endpoint> HTTP/1.1
Host: app.makeshift.ca
Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b
```

```shell
curl -X GET \
  'https://app.makeshift.ca/api/public/v2/<endpoint>' \
  -H 'Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b'
```


A MakeShift API token can be retrieved for any company admin using an API key and secret.

<aside class="notice">
  Note that authentication should happen against MakeShift's central auth system <a href="https://id.makeshift.ca">https://id.makeshift.ca</a>
</aside>

Use the returned token in API requests using an HTTP `Authorization` header, like so:

`Authorization: Bearer c1230734cc726edc6ae0f8fd00b279dc67f34937d7b8fa8fe5b13a232c11a04b`

## Token Info and Expiration

> To request token information:

```http
GET /oauth/token/info HTTP/1.1
Host: id.makeshift.ca
Content-Type: application/json
Authorization: Bearer 41abb4255ec9ea9cfee4f180206b30d6803f04e94eb46f7b58b158eae783d095
```

```shell
curl -X GET \
  https://id.makeshift.ca/oauth/token/info \
  -H 'Authorization: Bearer 41abb4255ec9ea9cfee4f180206b30d6803f04e94eb46f7b58b158eae783d095' \
  -H 'Content-Type: application/json' \
  -H 'Host: id.makeshift.ca' \
```

> Response example (valid):

```json
{
    "resource_owner_id": 7443,
    "scopes": [],
    "expires_in_seconds": 58,
    "application": {
        "uid": null
    },
    "created_at": 1558559900
}
```

> Response example (invalid):

```json
{
  "errors": [
    {
      "title": "Token is invalid.",
      "status_code": 401
    }
  ]
}
```

To easily determine if a token is valid and how much time is left before expiration use the `https://id.makeshift.ca/oauth/token/info` endpoint.

Please note the tokens currently remaining active for **4 hours** and will then expire. 

Using an invalid token (whether expired, revoked or simply incorrect) will result in a `401 Unauthorized` response. An example is provided to the right.

In order to refresh an expired token simply re-authenticate and get new token. It is also possible (and recommended) to check the `expires_in_seconds` property returned from `/oauth/token/info` in order to preemptively get a fresh token before expiration occurs.  
