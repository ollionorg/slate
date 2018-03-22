# Auth

## Check Auth

This api provides a mechanism to get the authorization status/access level of the request url by retreiving the
header information and checking the already set rules.

GoodCop provides a precedance specification according to the type of entity as shown:

1. **User > Group > Product**
2. **Tenant > API**

GoodCop also provides a mechanism to specify wildcard while setting rules.
**Wildcard used `*`**


Lets take few examples to illustrate the above.

**Example 1 :**

As a company you have specified the below rules:

1. `GET` request for url `/organization/blog` is set to `true` for `group1`.(Assuming user1 is part of group1)
2. `GET` request for url `/organization/blog` is set to `false` for `user1`.

In the above case, if `user1` request for url `/organization/blog`, will the user has access to the
above url.  
As per GoodCop precedance sepcification `1` the user will not have access to the url because as per precedance User has more
priority over Group, hence `false`.

**Example 2 :**

As a company you have specified the below rules:

1. `PUT` request for url `/organization/*` is set to `true` for `group1`.

In the above case, if `user1` within `group1` request for url `/organization/blog`, will the user has access to the above url.  
As per GoodCop Wildcard mechanism any url after `/organization/`(inclusive) will be given access, hence `true`.


> Definition

```
GET  https://[GOODCOP_URL]/v1/auth

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/auth"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'verb: PUT'
  -H 'path: /organization/*'
  -H 'user-token: test_rFU7Xu347hJL9UcFon1FzywvyA_8lERRhUWrf3cWivPLXaQ=='
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "effect": "true",
}

```

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/auth`


### Returns

Returns boolean value if a valid authorization key and a valid identifier was provided, and returns an error otherwise.
