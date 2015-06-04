---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://app.happyapps.io/signup/show'>Sign up for API Access</a>

includes:
  - checks
  - pushchecks
  - check_types
  - groups
  - apps
  - incidents
  - errors

search: true
---

# Introduction

Thank you for checking out Happy Apps. This page provides documentation for the full coverage Happy Apps API. It is an OAUTH 2.0 compatible REST API with support for manipulating almost all aspects of a users account. Create checks, groups, apps, get stats, incidents, settings, and even push check status updates for the PUSH based check type.

# Authentication

The Happy Apps API follows the OAuth 2.0 Specification and acts as an OAUTH 2.0 provider. To authorize your account you will need to use the same credentials you normally use to login to happy apps which will provide you with an `accessToken` as well as a `refreshToken`

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl -X POST --data "username=meow&password=meow" "https://api.happyapps.io/oauth/token?grant_type=password&scope=write&client_id=ha-customer"

#Returns:
{
  "access_token": "d0cc2cc4-f7f5-4713-a874-34491e7707de",
  "expires_in": 31535996,
  "refresh_token": "cda88865-f88d-4ed9-a621-424d9361beb2",
  "scope": "write",
  "token_type": "bearer"
}
```

> Make sure to replace `meow` with your username and password.

Happy apps expects all api requests to use the resultant `access_token` from the request made during authentication. This can be passed via the `Authorization` header. Be sure to replace the `access_token` with the actual token received from the OAuth request.

`Authorization: BEARER access_token`

<aside class="notice">
You must replace <code>access_token</code> with your generated Access Token.
</aside>

