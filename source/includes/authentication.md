# Authentication Process

## Getting an access token
```json
// Request
{
    "client_id": "",
    "client_secret": ""
}
```

```json
// Response
{
    "access_token": ""
}
```

If an endpoint requires authentication (which is the default in our API) then you'll need an access token.

To do this you need to make a POST request to `/auth/verify-client-credentials` with the client id and client secret encoded in the body. It will return a JSON object with an access token.

## Using an access token
To use the access token place it directly in the Authorization header (you do not need to prefix it with Bearer or anything else)