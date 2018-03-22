# User

## Sign Up Using Email and Password

> Definition

```
POST  https://api.goodcop.com/v1/signup

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/signup"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
       "email":"test", 
       "password":"test@#987"
    }'
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

## SignIn UsingGitHub

> Definition

```
POST  https://api.goodcop.com/v1/user/signin/github

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/signin/github"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://github.com/login/oauth/authorize?access_type=online&approval_prompt=auto&client_id=2857b5e2c2a665741368&redirect_uri=http%3A%2F%2Fa2c77437.ngrok.io%2Fv1%2Fcallback%2Fgithub&response_type=code&scope=user&state=eyJib2R5Ijoie1xuXHRcIm1ldGFcIjpcInVwZGF0ZWQgYXBpIG1ldGFcIlxufSIsInByb2R1Y3RUb2tlbiI6IjF5NHkydmE4dmZaNGoxQ2kxcXZHcmVRLXU4T3dEM0xqWVE5a3NlZ3hFcDA9In0%3D_a50b822630358ec4b16cc66f8e7d51c9508f3ed1"
}

```

Creates a user object provided once authorized by github using the redirect url.

### HTTPS Request

`POST https://api.goodcop.com/v1/signin/github`

### Returns

Returns user object from github, and returns an error otherwise.

## SignIn Google


> Definition

```
POST  https://api.goodcop.com/v1/user/signin/google

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/signin/google"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://accounts.google.com/o/oauth2/auth?access_type=online&approval_prompt=auto&client_id=581118883872-dgnlvtv9l8h3j0m7nipgtcoot3rgcc41.apps.googleusercontent.com&redirect_uri=http%3A%2F%2Fa2c77437.ngrok.io%2Fv1%2Fcallback%2Fgoogle&response_type=code&scope=https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.email+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.profile&state=eyJib2R5Ijoie1xuXHRcIm1ldGFcIjpcInVwZGF0ZWQgYXBpIG1ldGFcIlxufSIsInByb2R1Y3RUb2tlbiI6IjF5NHkydmE4dmZaNGoxQ2kxcXZHcmVRLXU4T3dEM0xqWVE5a3NlZ3hFcDA9In0%3D_a50b822630358ec4b16cc66f8e7d51c9508f3ed1"
}

```

Creates a user object provided once authorized by google using the redirect url.

### HTTPS Request

`POST https://api.goodcop.com/v1/signin/google`

### Returns

Returns user object from google, and returns an error otherwise.

## SignIn Facebook

> Definition

```
POST  https://api.goodcop.com/v1/user/signin/facebook

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/signin/facebook"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "to be updated"
}

```

Creates a user object provided once authorized by facebook using the redirect url.

### HTTPS Request

`POST https://api.goodcop.com/v1/signin/facebook`

### Returns

Returns user object from facebook, and returns an error otherwise.

## SignIn Twitter

> Definition

```
POST  https://api.goodcop.com/v1/user/signin/twitter

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/signin/twitter"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://api.twitter.com/oauth/authorize?oauth_token=a54r3gAAAAAA4-PrAAABYkvwDWA"
}

```

Creates a user object provided once authorized by twitter using the redirect url.

### HTTPS Request

`POST https://api.goodcop.com/v1/signin/twitter`

### Returns

Returns user object from twitter, and returns an error otherwise.

## SignIn Instagram

> Definition

```
POST  https://api.goodcop.com/v1/user/signin/instagram

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/signin/instagram"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "to be updated"
}

```

Creates a user object provided once authorized by instagram using the redirect url.

### HTTPS Request

`POST https://api.goodcop.com/v1/signin/instagram`

### Returns

Returns user object from instagram, and returns an error otherwise.

## SignIn Using MagicLink

> Definition

```
POST  https://api.goodcop.com/v1/user/magiclink

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/magiclink"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
       "email":"some_email@mail.com", 
    }'
```

> Example Response

```json
{
    "message": "Magic link sent to email successfully"
}
```

A magic link is sent to user email to sign in.

### HTTPS Request

`POST https://api.goodcop.com/v1/signup/magiclink`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | The email address to send to sign in. 

### Returns

Returns user object if correct email was provided, and returns an error otherwise.


## Sign Up PhoneNumber

> Definition

```
POST  https://api.goodcop.com/v1/user/signin/phone

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/signin/phone"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
       "phoneNumber":"+917678788789", 
    }'
```

> Example Response

```json
{
	"message": "OTP sent to your mobile successfully"
}

```

GoodCop will send the sms with a auto genrated otp. User needs to verfiy the otp against the phone number to 
sign in the user

### HTTPS Request

`POST https://api.goodcop.com/v1/user/signin/phone`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
phoneNumber | required | string | Phone number to send otp 

### Returns

Returns the success message if correct phone number is provided otherwise return 
will be an error.

## Verfiy PhoneNumber

> Definition

```
POST  https://api.goodcop.com/v1/user/signin/phone/verify

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/signin/phone/verify"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
       "phoneNumber":"+917678788789", 
       "otp":"878787"
    }'
```

> Example Response

```json
{
	"message": "to be updated"
}

```

User will verify the authenticity by verifying the otp.

### HTTPS Request

`POST https://api.goodcop.com/v1/user/signin/phone/verify`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
phoneNumber | required | string | Phone number of the user 
otp | required | string | otp sent to user mobile

### Returns

Returns the user object if phonenumber was verified with otp provided otherwise return 
will be an error.


## Login

> Definition

```
POST  https://api.goodcop.com/v1/user/login

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/login"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
       "email":"test", 
       "password":"test@#987"
    }'
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

`POST https://api.goodcop.com/v1/user/login`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | The email address to validate against. 
password | required | string | The password to authenticate user. 

### Returns

Returns the user object. In case of any validation of invalid email or password, the return 
will be an error.

## Change Password

> Definition

```
POST  https://api.goodcop.com/v1/user/passwordChange

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/passwordChange"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'user-token: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
  -d '{
       "oldapassword":"test", 
       "newpassword":"test@#987"
    }'
```

> Example Response

```json
{
   "message":"Password Changed Successfully"
}
```

Change the password for the logged in user providing the oldpassword and new password.
### HTTPS Request

`POST https://api.goodcop.com/v1/user/passwordChange`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
oldapassword | required | string | The old password of the user. 
newapassword | required | string | The new password to to set. 

### Returns

Returns the string message. In case of any validation of invalid oldpassword, the return 
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
  -X POST
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
  -X POST
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
  -d '{
	"meta":"storing test meta info"
    }'
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
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
    }]'
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
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
    }]'
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