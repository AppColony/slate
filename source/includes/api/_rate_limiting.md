# Rate Limiting

The MakeShift API is currently limited to a call rate of 100 requests per minute. All API calls sharing a token count towards the rate limit, regardless of the HTTP method (`GET`, `POST`, etc.). Calls exceeding the rate limit will fail and return a status code of `429 Too Many Requests` and the response shown at right.

> Response when rate limit exceeded

```json
{
    "errors": [
        {
            "title": "Rate limit exceeded",
            "status": "429"
        }
    ]
}
```
