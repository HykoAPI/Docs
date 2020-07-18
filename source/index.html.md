---
title: Hyko API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - go

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the Hyko API! This document describes how your application can integrate with Hyko.

You can view code examples in the dark area to the right.

Get started with an overview of how our Authentication works.

<aside class="warning">
The Hyko API is currently being written and is not yet ready for use. We'd love to hear your feedback and suggestions. For now, you can let us know at whoisnazm@gmail.com.
</aside>

# Authentication

> To authorize, use this code:

```shell
# With shell, you can simply pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: woofwoof"
```

```go
import "hyko"

api := hyko.authorize("woofwoof");
```

> Make sure to replace `woofwoof` with your API key.

The Hyko API implements [OAuth 2.0](https://oauth.net/2/) to allow users to log in to applications without exposing their credentials.

The process involves several steps:

1. Acquire an access token, and optionally a refresh token
2. Use the access token to make authenticated requests
3. If you were issued a refresh token: refresh the access token when it expires

Hyko expects for the access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: woofwoof`

<aside class="notice">
You must replace <code>woofwoof</code> with your personal API key.
</aside>

# Users

## Get All Users

```shell
curl "http://example.com/api/users"
  -H "Authorization: woofwoof"
```

```go
import "hyko"

api := hyko.authorize("woofwoof");
users := api.hyko.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "company_id": "user_001",
    "first_name": "Ollie",
    "surname": "Woofer"
  },
  {
    "id": 2,
    "company_id": "user_002",
    "first_name": "Lester",
    "surname": "Fitzpatrick"
  }
]
```

This endpoint retrieves all puppys.

### HTTP Request

`GET http://example.com/api/puppys`

### Query Parameters

| Parameter    | Default | Description                                                                     |
| ------------ | ------- | ------------------------------------------------------------------------------- |
| include_cats | false   | If set to true, the result will also include cats.                              |
| available    | true    | If set to false, the result will include puppys that have already been adopted. |

<aside class="success">
Remember — a happy puppy is an authenticated puppy!
</aside>

## Get a Specific Puppy

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.puppys.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.puppys.get(2)
```

```shell
curl "http://example.com/api/puppys/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let max = api.puppys.get(2);
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

This endpoint retrieves a specific puppy.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/puppys/<ID>`

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the puppy to retrieve |

## Delete a Specific Puppy

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.puppys.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.puppys.delete(2)
```

```shell
curl "http://example.com/api/puppys/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let max = api.puppys.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted": ":("
}
```

This endpoint deletes a specific puppy.

### HTTP Request

`DELETE http://example.com/puppys/<ID>`

### URL Parameters

| Parameter | Description                   |
| --------- | ----------------------------- |
| ID        | The ID of the puppy to delete |
