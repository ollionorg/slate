---
title: GoodCop API Reference

language_tabs:
  - cURL

toc_footers:
  - <a href='#'>GoodCop Api Documentation</a>
  - <a href=''>Documentation by CloudCover</a>

includes:
  - user
  - group
  - product
  - tenant
  - api
  - org
  - auth
  - errors
  

search: true
---

# GoodCop API Reference

The GoodCop API is organized around REST. Our API has resource-oriented URLs, and uses HTTPS response codes to indicate API errors. We use built-in HTTPS features, like HTTPS authentication and HTTPS verbs, which are understood by off-the-shelf HTTPS clients. JSON is returned by all API responses, including errors.


# Authentication

> To authorize, use this code:

```shell
> Example Request
curl "api_endpoint_here"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs="
```

> Make sure to replace Authorization header with your Product API key.

Authenticate your account when using the GoodCop API by including your Product Authorization key in the request.
GoodCop expects for the Authorization key to be included in all API requests to the server in header that looks like the following:

`Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=`

<aside style="background:#5bc0de;">
You must replace <code style="#000000;">test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=</code> with your product authorization key.
</aside>