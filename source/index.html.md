---
title: GoodCop API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>GoodCop Api Documentation</a>
  - <a href=''>Documentation by CloudCover</a>

includes:
  - errors

search: true
---

# API Reference

The GoodCop API is organized around REST. Our API has resource-oriented URLs, and uses HTTPS response codes to indicate API errors. We use built-in HTTPS features, like HTTPS authentication and HTTPS verbs, which are understood by off-the-shelf HTTPS clients. JSON is returned by all API responses, including errors.


# Authentication

> To authorize, use this code:

```shell
> Example Request
curl "api_endpoint_here"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs="
```

> Make sure to replace Authorization header with your Product API key.

Authenticate your account when using the API by including your Product API key in the request.
GoodCop expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=`

<aside style="background:#5bc0de;">
You must replace <code style="#000000;">test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=</code> with your product API key.
</aside>

# User

## Sign Up Using Email and Password

> Definition

```
POST  https://api.goodcop.com/v1/signup

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/signup"
  -d '{"email":"test", "password":"test@#987"}'
  -X "POST"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": [],
    "groups": [],
    "meta": "",
    "token": "test_IDvekbzln82kvCPKxv6-lYwovmucoRVlPtRlKAoo1N13l3PgfaxJeprTtfHgihddKfITPrgDvre8RKM8w==",
    "verified": false
}
```

Creates a user object provided the email and password in the request body and returns the user object.

### HTTPS Request

`POST https://api.goodcop.com/v1/signup`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | The email address to send the verfication. 
password | required | string | The password to set for the user to authenticate. 

### Returns

Returns user object if correct email and password was provided, and returns an error otherwise.

## Sign Up UsingGitHub
## Sign Up Google


## Login

> Definition

```
POST  https://api.goodcop.com/v1/login

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/login"
  -d '{"email":"test", "password":"test@#987"}'
  -X "POST"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": null,
    "groups": null,
    "meta": "",
    "token": "eUhWVAYVcw_guO-XRLs_JIZimSiXycUAesf0VkBNptZvhZQnkC0uZacvuhtj8BVI2m5YoHbCU_AU_3hK-tytRg==",
    "verified": false
}
```

Authenticates the user provided the valid email and password and Retrieves the details of a user that has previously been created.

### HTTPS Request

`POST https://api.goodcop.com/v1/login`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | The email address to validate against. 
password | required | string | The password to authenticate user. 

### Returns

Returns the user object. In case of any validation of invalid email or password, the return 
will be an error.

## Get User By ID

Retrieves the details of a user that has previously been created. Provide the unique user ID that was returned from your login request and Goodcop will return the corresponding user information.

> Definition

```
GET  https://api.goodcop.com/v1/user/{userID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": null,
    "groups": null,
    "meta": "",
    "token": "eUhWVAYVcw_guO-XRLs_JIZimSiXycUAesf0VkBNptZvhZQnkC0uZacvuhtj8BVI2m5YoHbCU_AU_3hK-tytRg==",
    "verified": false
}
```

### HTTPS Request

`POST https://api.goodcop.com/v1/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns user if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get User By Email

Retrieves the details of a user that has previously been created. Provide the unique email that was returned from your login request and Goodcop will return the corresponding user information.

> Definition

```
GET  https://api.goodcop.com/v1/user/{email}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test@mail.com"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": null,
    "groups": null,
    "meta": "",
    "token": "eUhWVAYVcw_guO-XRLs_JIZimSiXycUAesf0VkBNptZvhZQnkC0uZacvuhtj8BVI2m5YoHbCU_AU_3hK-tytRg==",
    "verified": false
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/user/{email}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | Valid email address 

### Returns

Returns user if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## List Users

Retrieves the details of all users that has previously been created.

> Definition

```
GET  https://api.goodcop.com/v1/user

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "users": [
        {
            "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
            "email": "test@mail.tv",
            "rules": [
                {
                    "verb": "PUT",
                    "path": "/credentials/new/smart/5687539843203072",
                    "effect": true
                }
            ],
            "groups":  [
                5647053199769600,
                5687905720729600
            ],
            "meta": "",
            "token": "usPAGnmuNtq8JXIprybHXq2c90uC6Jxr62DFv9CpwFO3S25x6WYdT20AZT1xVE1rmSMT5ZwxQhT7sgo5-S42ag==",
            "verified": false
        },
        {
              "userId": "test1_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
              "email": "test1@mail.com",
              "rules": null,
              "groups": null,
              "meta": "",
              "token": "eUhWVAYVcw_guO-XRLs_JIZimSiXycUAesf0VkBNptZvhZQnkC0uZacvuhtj8BVI2m5YoHbCU_AU_3hK-tytRg==",
              "verified": false
        },
            ]
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/user`

### Returns

Returns list of user objects if a valid authorization key was provided, and returns an error otherwise.

## Delete User By ID

Provide the unique user ID and Goodcop will return the message for successful deletion of user.

> Definition

```
DELETE  https://api.goodcop.com/v1/user/{userID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "User deleted successfully"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Get Group Details By ID

Provide the unique user ID and Goodcop will return the group details.

> Definition

```
GET  https://api.goodcop.com/v1/user/{userID}/groups

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/groups"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
[
    {
        "groupId": 5717800035287040,
        "name": "CloudCover",
        "description": "",
        "rules": [
            {
                "verb": "PUT",
                "path": "/credentials/new/smart/5687539843203072",
                "effect": false
            },
            {
                "verb": "PUT",
                "path": "/credentials/new/smart/*",
                "effect": true
            }
        ],
        "meta": "",
        "productId": 5750501782061056
    },
    {
        "groupId": 5664530495438848,
        "name": "CloudCover|admin",
        "description": "",
        "rules": [
            {
                "verb": "PUT",
                "path": "/organizations/5717800035287040",
                "effect": true
            },
            {
                "verb": "PUT",
                "path": "/organizations/5664530495438848",
                "effect": true
            }
        ],
        "meta": "",
        "productId": 5750501782061056
    }
]
```

### HTTPS Request

`GET https://api.goodcop.com/v1/user/{userID}/groups`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns a array of groups if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Get User Meta By ID

Provide the unique user ID and Goodcop will return the meta details.

> Definition

```
GET  https://api.goodcop.com/v1/user/{userID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/meta"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "meta": "storing test meta info",
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/user/{userID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string | The email address to send the verfication. 

### Returns

Returns meta if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update User Meta By ID

Provide the unique user ID and Goodcop will return the meta details.

> Definition

```
PUT  https://api.goodcop.com/v1/user/{userID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ],
    "groups": [
        5717800035287040,
        5664530495438848,
    ],
    "meta": "storing test meta info",
    "token": "wv0X3yJCKhzFxX92vRVs4ube944zY3YJCVtI1EAUBXTQpXrGEFmNdFSLyk6ygA7CDaK8sbN8xHhkxuwBUu5xNQ==",
    "verified": false
}
```

### HTTPS Request

`PUT https://api.goodcop.com/v1/user/{userID}/meta`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string | Metadata to be stored for the user

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns user object with updated meta if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## List User Rules By ID

Provide the unique user ID and Goodcop will return the list of all rules.

> Definition

```
GET  https://api.goodcop.com/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "rules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/user/{userID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns rules object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update User Rules By ID

Provide the unique user ID and Goodcop will return the updated list of all rules.

> Definition

```
PUT  https://api.goodcop.com/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/rule"
  -X PUT
  -d '[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        }]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ],
    "groups": [
        5717800035287040,
        5664530495438848,
    ],
    "meta": "storing test meta info",
    "token": "wv0X3yJCKhzFxX92vRVs4ube944zY3YJCVtI1EAUBXTQpXrGEFmNdFSLyk6ygA7CDaK8sbN8xHhkxuwBUu5xNQ==",
    "verified": false
}
```

### HTTPS Request

`PUT https://api.goodcop.com/v1/user/{userID}/rule`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns user object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Delete User Rules By ID

Provide the unique user ID and Goodcop will return the updated list of all rules.

> Definition

```
DELETE  https://api.goodcop.com/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/rule"
  -X DELETE
  -d '[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        }]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": [
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ],
    "groups": [
        5717800035287040,
        5664530495438848,
    ],
    "meta": "storing test meta info",
    "token": "wv0X3yJCKhzFxX92vRVs4ube944zY3YJCVtI1EAUBXTQpXrGEFmNdFSLyk6ygA7CDaK8sbN8xHhkxuwBUu5xNQ==",
    "verified": false
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/user/{userID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns user object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Get Group Details for user By ID

Provide the unique user ID and Goodcop will return the list of all groups.

> Definition

```
GET  https://api.goodcop.com/v1/user/{userID}/groups

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/groups"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
[
    {
        "groupId": 5198802495471616,
        "name": "admin",
        "description": "",
        "rules": null,
        "meta": "",
        "productId": 5750501782061056
    },
    {
        "groupId": 5631639635886080,
        "name": "general",
        "description": "",
        "rules": [
            {
                "verb": "GET",
                "path": "/organizations/5714163003293696/*",
                "effect": true
            }
        ],
        "meta": "",
        "productId": 5750501782061056
    },
    {
        "groupId": 5673202705498112,
        "name": "editor",
        "description": "",
        "rules": [
            {
                "verb": "PUT",
                "path": "/organizations/5714163003293696/*",
                "effect": true
            },
            {
                "verb": "POST",
                "path": "/organizations/5714163003293696/*",
                "effect": true
            }
        ],
        "meta": "",
        "productId": 5750501782061056
    }
]

```

### HTTPS Request

`GET https://api.goodcop.com/v1/user/{userID}/groups`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns array of group details with a valid authorization key and a valid identifier was provided, and returns an error otherwise.

# Group

## Create Group

> Definition

```
POST  https://api.goodcop.com/v1/group

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group"
  -d '{
	"name":"test_group",
    "rules":[
		{"path":"thrifty/billing","verb":"GET","effect":true}
	]
    }'
  -X "POST"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "groupId": 5707274949492736,
    "name": "test_group",
    "description": "",
    "rules": [
        {
            "verb": "GET",
            "path": "/thrifty/billing",
            "effect": true
        }
    ],
    "meta": "",
    "productId": 5750501782061056
}
```

Creates a group object provided the name in the request body and returns the group object.

### HTTPS Request

`POST https://api.goodcop.com/v1/group`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | The name of the group. Group with same name can be created.
rule | optional | array | The rules to set for the group
description | optional | string | The Description of the group
meta | optional | string | Provide metadata to store against the group
 

### Returns

Returns group object if correct type of name is provided, and returns an error otherwise.

## Get Group By ID

Retrieves the details of a group that has previously been created. Provide the unique group ID that was returned from your login request and Goodcop will return the corresponding user information.

> Definition

```
GET  https://api.goodcop.com/v1/group/{groupID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5707274949492736"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "groupId": 5707274949492736,
    "name": "test_group1",
    "description": "",
    "rules": [
        {
            "verb": "GET",
            "path": "/thrifty/billing",
            "effect": true
        }
    ],
    "meta": "",
    "productId": 5750501782061056
}

```

### HTTPS Request

`GET https://api.goodcop.com/v1/group/{groupID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns group details if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## List Groups

Retrieves the details of all groups that has previously been created.

> Definition

```
GET  https://api.goodcop.com/v1/group

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json

{
    "groups": [
        {
            "groupId": 4889147835678720,
            "name": "admin",
            "description": "",
            "rules": null,
            "meta": "",
            "productId": 5750501782061056
        },
        {
            "groupId": 5707274949492736,
            "name": "test_group1",
            "description": "",
            "rules": [
                {
                    "verb": "GET",
                    "path": "/thrifty/billing",
                    "effect": true
                }
            ],
            "meta": "",
            "productId": 5750501782061056
        }
    ]
}

```

### HTTPS Request

`GET https://api.goodcop.com/v1/group`

### Returns

Returns list of group objects if a valid authorization key was provided, and returns an error otherwise.

## Delete Group By ID

Provide the unique group ID and Goodcop will return the message for successful deletion of group.

> Definition

```
DELETE  https://api.goodcop.com/v1/group/{groupID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5707274949492736"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "Group has been deleted for groupID - 5707274949492736"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/group/{groupID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Multiple Group

Provide the unique array of group IDs and Goodcop will return the message for successful deletion of group.

> Definition

```
DELETE  https://api.goodcop.com/v1/group

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group"
  -X DELETE
  -d '[5717800035287040,5717800035287766]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "Groups Deleted Successfully"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/group`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupIDs | array | integer | Array of Valid group identifiers

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Add Multiple Users to Group By ID

Provide the unique group ID and Goodcop will add multiple users to the group.

> Definition

```
PUT  https://api.goodcop.com/v1/group/{groupID}/user

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5707274949492736/user"
  -X PUT
  -d '{ "users":[
                    "01e097a1-fedd-466f-96c9-3eaee6cc7f1f",
                    "022fa660-9242-4521-b614-e46ffead2b2b"
                ]
    }'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "users": [
        {
            "error": null,
            "userId": "test_a660-9242-4521-b614-e46ffead2b2b",
            "message": "Group added successfully"
        },
        {
            "error": null,
            "userId": "test1_97a1-fedd-466f-96c9-3eaee6cc7f1f",
            "message": "Group added successfully"
        }
    ]
}
```

### HTTPS Request

`PUT https://api.goodcop.com/v1/group/{groupID}/users`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
users | required | string array | Valid user indentifier array

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns a object with updated mesage if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Add Single User to Group By Email

Provide the unique email address and Goodcop will add the user to the specified group.

> Definition

```
PUT  https://api.goodcop.com/v1/group/{groupID}/userEmail

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5707274949492736/userEmail"
  -X PUT
  -d '{ 
	"email":"test@mail.com"
    }'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "user": "test_a660-9242-4521-b614-e46ffead2b2b"
}

```

### HTTPS Request

`PUT https://api.goodcop.com/v1/group/{groupID}/userEmail`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | Valid email address

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns a user ID to which was added if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Get User for Group By ID

Provide the unique user ID, Group ID and Goodcop will return the user details.

> Definition

```
GET  https://api.goodcop.com/v1/group/{groupID}/user/{userID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/user/test_a660-9242-4521-b614-e46ffead2b2b"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_a660-9242-4521-b614-e46ffead2b2b",
    "email": "test@mail.com",
    "rules": null,
    "groups": [
        5717800035287040
    ],
    "meta": "",
    "token": "usPAGnmuNtq8JXIprybHXq2c90uC6Jxr62DFv9CpwFO3S25x6WYdT20AZT1xVE1rmSMT5ZwxQhT7sgo5-S42ag==",
    "verified": false
}

```

### HTTPS Request

`GET  https://api.goodcop.com/v1/group/{groupID}/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 
userID | required | string | Valid user identifier 

### Returns

Returns user object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Get All Users for Group By ID

Provide the unique Group ID and Goodcop will return the list of user details.

> Definition

```
GET  https://api.goodcop.com/v1/group/{groupID}/user

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/user"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "users": [
        {
            "userId": "test_a660-9242-4521-b614-e46ffead2b2b",
            "email": "test@mail.com",
            "rules": null,
            "groups": [
                5717800035287040
            ],
            "meta": "",
            "token": "usPAGnmuNtq8JXIprybHXq2c90uC6Jxr62DFv9CpwFO3S25x6WYdT20AZT1xVE1rmSMT5ZwxQhT7sgo5-S42ag==",
            "verified": false
        },
        {
            "userId": "test1_a660-9242-4521-b614-e46ffead2b2b",
            "email": "test1@mail.com",
            "rules": [
                {
                    "verb": "GET",
                    "path": "/users/254c244a-bc58-43d2-a85e-378dc6195795/*",
                    "effect": true
                },
                {
                    "verb": "PUT",
                    "path": "/users/254c244a-bc58-43d2-a85e-378dc6195795/*",
                    "effect": true
                },
                {
                    "verb": "DELETE",
                    "path": "/users/254c244a-bc58-43d2-a85e-378dc6195795/*",
                    "effect": true
                }
            ],
            "groups": [
                5204687808626688,
                5663311798468608,
                5762893836451840,
                5717800035287040
            ],
            "meta": "",
            "token": "Mo6Z-QWu5Lgpm14tDaP1Wz_Rz-pyLOae6LVTheWKxSJI4Vmfqfdrn0NfZ1niOr3f8mwrG791EOcTiEY2jbdgMw==",
            "verified": false
        }
    ]
}

```

### HTTPS Request

`GET  https://api.goodcop.com/v1/group/{groupID}/user`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 


### Returns

Returns list of user object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete User from Group By ID

Provide the unique user ID and Goodcop will return the message for successful deletion of user.

> Definition

```
DELETE  https://api.goodcop.com/v1/group/{groupID}/user/{userID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/user/test_a660-9242-4521-b614-e46ffead2b2b"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "Group deleted successfully"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/group/{groupID}/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 
userID | required | string | Valid user identifier 

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get Group Meta By ID

Provide the unique group ID and Goodcop will return the meta inforamtion for the group.

> Definition

```
GET  https://api.goodcop.com/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "meta": "test meta"

```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/group/{groupID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns a meta string if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Update Group Meta By ID

Provide the unique user ID and Goodcop will return the meta details.

> Definition

```
PUT  https://api.goodcop.com/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/meta"
  -X PUT
  -d '{
	"meta":"update test meta"
    }'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "meta": "update test meta"
}

```

### HTTPS Request

`PUT https://api.goodcop.com/v1/group/{groupID}/meta`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string | Metadata to be updated for the group

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns string with updated meta if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Delete Group Meta By ID

Provide the unique group ID, meta and Goodcop will return the group details with empty meta.

> Definition

```
DELETE  https://api.goodcop.com/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/meta"
  -X DELETE
  -d '{
	"meta":"update test meta"
    }'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "groupId": 5717800035287040,
    "name": "admin",
    "description": "",
    "rules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ],
    "meta": "",
    "productId": 5750501782061056
}

```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/group/{groupID}/meta`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string | Metadata to be deleted for the group

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns group object with deleted meta if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get Group Rules By ID

Provide the unique group ID and Goodcop will return the list of all rules.

> Definition

```
GET  https://api.goodcop.com/v1/group/{groupID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "rules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/group/{groupID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns rules object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Group Rules By ID

Provide the unique user ID and Goodcop will return the updated list of all rules.

> Definition

```
PUT  https://api.goodcop.com/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/rule"
  -X PUT
  -d '[{
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "rules": [
     {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
}

```

### HTTPS Request

`PUT https://api.goodcop.com/v1/group/{groupID}/rule`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns update rules object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Group Rules By ID

Provide the unique group ID, rule array and Goodcop will return the updated list of all rules.

> Definition

```
DELETE  https://api.goodcop.com/v1/group/{groupID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/group/5717800035287040/rule"
  -X DELETE
  -d '[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        }]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "rules": [
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/group/{groupID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns updated rules object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

# Product

## List Products

Retrieves the details of all products that has previously been created. 

<aside style="background:#f0ad4e;">
The Authorization token is a super secure token that is only accessible to administrators of Goodcop Api.
</aside>


> Definition

```
GET  https://api.goodcop.com/v1/product

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/product"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "Products": [
        {
            "id": 5735995932672000,
            "name": "product_1",
            "description": "product_1",
            "authCallback": "https://requestb.in/1f4y9ho1",
            "apiRules": [
                {
                    "verb": "POST",
                    "path": "/product_1/billing",
                    "effect": false
                },
                {
                    "verb": "POST",
                    "path": "/product_1/billin",
                    "effect": true
                },
                {
                    "verb": "POST",
                    "path": "/dkd",
                    "effect": false
                }
            ],
            "apiMeta": "123",
            "userRules": null,
            "userMeta": "",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "FIaxZkJNOmj3MjPNgo2tFvZOXvWbNAdlAWWaAZnb9fg="
                }
            ]
        },
        {
            "id": 5760586365272064,
            "name": "product_2",
            "description": "product_2",
            "authCallback": "",
            "apiRules": null,
            "apiMeta": "",
            "userRules": [
                {
                    "verb": "GET",
                    "path": "/hello/hi",
                    "effect": true
                }
            ],
            "userMeta": "",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "II4htdb2eUx0FKDrA7Fr0INyd4WsamLlrzCIjKW8fTI="
                }
            ]
        },
        {
            "id": 5750501782061056,
            "name": "product_3",
            "description": "product_3",
            "authCallback": "",
            "apiRules": null,
            "apiMeta": "",
            "userRules": null,
            "userMeta": "",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "aIsKmHDTaSvYJ7JBzc5_QsnJZ4UWJFwMgt5AIA4Oyvs="
                }
            ]
        }
    ]
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/product`

### Returns

Returns list of products if a valid authorization key was provided, and returns an error otherwise.

## Create Product

> Definition

```
POST  https://api.goodcop.com/v1/product

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/product"
  -d '{
	"name":"test_product"
    }'
  -X "POST"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "id": 6308443803615232,
    "name": "test_product",
    "description": "",
    "authCallback": "",
    "apiRules": null,
    "apiMeta": "",
    "userRules": null,
    "userMeta": "",
    "apiKeys": [
        {
            "name": "default",
            "value": "test_2va8vfZ4j1Ci1qvGreQ-u8OwD3LjYQ9ksegxEp0="
        }
    ]
}

```

Creates a product provided the name in the request body.

<aside style="background:#f0ad4e;">
The Authorization token is a super secure token that is only accessible to administrators of Goodcop Api.
</aside>

### HTTPS Request

`POST https://api.goodcop.com/v1/group`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | The name of the product.
 

### Returns

Returns product object if correct type of name is provided, and returns an error otherwise.

## Get Product By ID

Retrieves the details of a product. Provide the unique product ID and Goodcop will return the corresponding user information.

> Definition

```
GET  https://api.goodcop.com/v1/product/{productID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/product/5735995932672000"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "id": 5735995932672000,
    "name": "product_1",
    "description": "123",
    "authCallback": "https://requestb.in/1f4y9ho1",
    "apiRules": [
        {
            "verb": "POST",
            "path": "/product_1/billing",
            "effect": false
        },
        {
            "verb": "POST",
            "path": "/product_1/billin",
            "effect": true
        },
        {
            "verb": "POST",
            "path": "/dkd",
            "effect": false
        }
    ],
    "apiMeta": "123",
    "userRules": null,
    "userMeta": "",
    "apiKeys": [
        {
            "name": "default",
            "value": "test_3MjPNgo2tFvZOXvWbNAdlAWWaAZnb9fg="
        }
    ]
}

```

### HTTPS Request

`GET https://api.goodcop.com/v1/product/{productID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns product detauls if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Product By ID

Provide the product details and Goodcop will return the updated product information.

> Definition

```
PUT  https://api.goodcop.com/v1/product/{productID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/product/6308443803615232"
  -X PUT
  -d '{
	"name":"test_product",
	"description":"This is test description",
	"apiMeta": "test meta",
	"authCallback":"/callback",
	"apiRules":[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
		
	}],
	"userRules":[{
            "verb": "GET",
            "path": "/new/5687539843203072",
            "effect": true
		
	}],
	"userMeta":"user meta"
    }'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
	"name":"test_product",
	"description":"This is test description",
	"apiMeta": "test meta",
	"authCallback":"/callback",
	"apiRules":[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
		
	}],
	"userRules":[{
            "verb": "GET",
            "path": "/new/5687539843203072",
            "effect": true
		
	}],
	"userMeta":"user meta"
}

```

### HTTPS Request

`PUT https://api.goodcop.com/v1/product/{productID}`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | optional | string | name of the product
description | optional | string |  description of the product 
authCallback | optional | string | define a callback for federated auth 
apiMeta | optional | string | meta information of the api 
apiRules | optional | array | rules of api
userMeta | optional | string | meta information of the user 
userRules | optional | array | rules of user  

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid user identifier 

### Returns

Returns product object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Product By ID

Provide the unique product ID and Goodcop will return the message for successful deletion of product.

> Definition

```
DELETE  https://api.goodcop.com/v1/product/{productID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/product/5178306911535104"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "Product Deleted Successfully"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/product/{productID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Meta By ID

Provide the unique product ID and Goodcop will return the meta details.

> Definition

```
PUT  https://api.goodcop.com/v1/product/{productID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/product/5178306911535104/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: user" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "meta updated successfully"
}
```
<aside style="background:#5bc0de;">
The category header can be provided with two options either api or user depending on which type meta you want to change 
</aside>

### HTTPS Request

`PUT https://api.goodcop.com/v1/product/{productID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns message string if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get Meta By ID



## Delete Meta By ID

## Get Rules By ID

## Update Rules By ID

## Delete Rules By ID

## Create APIKey By ID

## Get APIKey By ID

## Get All APIKeys By ID

## Delete APIKeys By ID

# Tenant

## Create Tenant

## Get Tenant By ID

## Delete Tenant By ID

## Get Rule By ID

## Update Rule By ID

## Delete Rule By ID

## Update Secret By ID

## Get Secret By ID

## Get Meta By ID

## Update Meta By ID

## Delete Meta By ID 

# Api

## Create Api

## Get Api By ID

## Get All Apis

## Delete Api By ID

## Get rule By ID

## Update rule By ID

## Delete rule By ID

## Get Meta By ID

## Update Meta By ID

## Delete Meta By ID

# Auth

## Check Auth