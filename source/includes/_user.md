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