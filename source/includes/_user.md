# User

The API allows you to create, delete, and update your users with addition of social providers and passwordless authentication using magic link. You can retrieve individual users as well as a list of all your users. Also the api gives ability to set authorization level privileges using the rules object.

## Signup using eamil and passowrd

> Definition

```
POST  https://dev.goodcop.com/v1/user/signup

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signup"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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
    "devicetokens": [
        {
            "token": "KHE-PdB5YpsUPYnudAzRMflS1n-gDzgvOgGSa5jvEKYRlirNtQ76Vurvq2GsM3FnmGdno7eKBltB0T047mbgKg==",
            "deviceid": "test_56789657567"
        }
    ],
    "verified": false,
    "createdAt": "2018-03-22T14:12:14.780714+05:30",
    "updatedAt": "2018-03-22T14:12:14.780716+05:30"
}
```

Creates a new user object.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signup`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | The email address to send the verfication. 
password | required | string | The password to set for the user to authenticate. 

### Returns

Returns a user object if correct email and password was provided. The returned object will have information about the rules, groups, metadata. If no email or password was provided, same email which already exists or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `Either email or password is missing`
3.  `Email is not valid`
4.  `Password must be atleast 7 characters long`
5.  `You are already registered with product1 and product2`


## SignIn using github

> Definition

```
POST  https://dev.goodcop.com/v1/user/signin/github

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signin/github"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://github.com/login/oauth/authorize?access_type=online&approval_prompt=auto&client_id=2857b5e2c2a665741368&redirect_uri=http%3A%2F%2Fa2c77437.ngrok.io%2Fv1%2Fcallback%2Fgithub&response_type=code&scope=user&state=eyJib2R5Ijoie1xuXHRcIm1ldGFcIjpcInVwZGF0ZWQgYXBpIG1ldGFcIlxufSIsInByb2R1Y3RUb2tlbiI6IjF5NHkydmE4dmZaNGoxQ2kxcXZHcmVRLXU4T3dEM0xqWVE5a3NlZ3hFcDA9In0%3D_a50b822630358ec4b16cc66f8e7d51c9508f3ed1"
}

```

Creates a new user object via github.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signin/github`

### Returns

Returns a redirect url. The redirect url will be used to authenticate the user using github. If the user is successfully authenticated using github, goodcop will redirect to the product callback. If no callback is set by the product, social auth provider failure or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `No Callback is set for your product, please set that first`

## SignIn using facebook


> Definition

```
POST  https://dev.goodcop.com/v1/user/signin/google

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signin/google"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://accounts.google.com/o/oauth2/auth?access_type=online&approval_prompt=auto&client_id=581118883872-dgnlvtv9l8h3j0m7nipgtcoot3rgcc41.apps.googleusercontent.com&redirect_uri=http%3A%2F%2Fa2c77437.ngrok.io%2Fv1%2Fcallback%2Fgoogle&response_type=code&scope=https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.email+https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fuserinfo.profile&state=eyJib2R5Ijoie1xuXHRcIm1ldGFcIjpcInVwZGF0ZWQgYXBpIG1ldGFcIlxufSIsInByb2R1Y3RUb2tlbiI6IjF5NHkydmE4dmZaNGoxQ2kxcXZHcmVRLXU4T3dEM0xqWVE5a3NlZ3hFcDA9In0%3D_a50b822630358ec4b16cc66f8e7d51c9508f3ed1"
}

```

Creates a new user object via google.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signin/google`

### Returns

Returns a redirect url. The redirect url will be used to authenticate the user using google. If the user is successfully authenticated using google, goodcop will redirect to the product callback. If no callback is set by the product, social auth provider failure or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `No Callback is set for your product, please set that first`

## SignIn using facebook

> Definition

```
POST  https://dev.goodcop.com/v1/user/signin/facebook

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signin/facebook"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://www.facebook.com/dialog/oauth?access_type=online&approval_prompt=auto&client_id=1715535545188089&redirect_uri=http%3A%2F%2Flocalhost%3A8080%2Fv1%2Fcallback%2Ffacebook&response_type=code&scope=email&state=eyJib2R5Ijoie1xuXHRcImVtYWlsXCI6IFwidmFpYmhhdkBjbG91ZGNvdmVyLmluXCJcbn0iLCJkZXZpY2VJZCI6IiIsInByb2R1Y3RUb2tlbiI6IkdRU05VQWpFUTNnU19uVXl6NXhvSUwwVlh3ZG9EUnRyajBLNkI1blJQcjQ9IiwidXNlclRva2VuIjoiIn0%3D_b88554542246d0c1a092a16c66ec960f4972364d"
}

```

Creates a new user object via facebook.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signin/facebook`

### Returns

Returns a redirect url. The redirect url will be used to authenticate the user using facebook. If the user is successfully authenticated using facebook, goodcop will redirect to the product callback. If no callback is set by the product, social auth provider failure or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `No Callback is set for your product, please set that first`

## SignIn using twitter

> Definition

```
POST  https://dev.goodcop.com/v1/user/signin/twitter

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signin/twitter"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://api.twitter.com/oauth/authorize?oauth_token=a54r3gAAAAAA4-PrAAABYkvwDWA"
}

```

Creates a new user object via twitter.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signin/twitter`

### Returns

Returns a redirect url. The redirect url will be used to authenticate the user using twitter. If the user is successfully authenticated using twitter, goodcop will redirect to the product callback. If no callback is set by the product, social auth provider failure or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `No Callback is set for your product, please set that first`

## SignIn using instagram

> Definition

```
POST  https://dev.goodcop.com/v1/user/signin/instagram

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signin/instagram"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json

{
    "redirectUrl": "https://api.instagram.com/oauth/authorize?access_type=online&approval_prompt=auto&client_id=71e9de2416cf498285fdce2414fcba79&redirect_uri=http%3A%2F%2F127.0.0.1%3A8080%2Fv1%2Fcallback%2Finstagram&response_type=code&scope=basic&state=eyJib2R5IjoiIiwiZGV2aWNlSWQiOiIiLCJwcm9kdWN0VG9rZW4iOiJHUVNOVUFqRVEzZ1NfblV5ejV4b0lMMFZYd2RvRFJ0cmowSzZCNW5SUHI0PSIsInVzZXJUb2tlbiI6IiJ9_17061fa5b0f196ab26b3ca2ca44259b4353a42dd"
}

```

Creates a new user object via instagram.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signin/instagram`

### Returns

Returns a redirect url. The redirect url will be used to authenticate the user using instagram. If the user is successfully authenticated using instagram, goodcop will redirect to the product callback. If no callback is set by the product, social auth provider failure or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `No Callback is set for your product, please set that first`

## SignIn using magiclink

> Definition

```
POST  https://dev.goodcop.com/v1/user/magiclink

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/magiclink"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

Creates a new user object via email by creating a token that will allow user to log in through the link sent to their email.


### HTTPS Request

`POST https://dev.goodcop.com/v1/signup/magiclink`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | The email address to send the magic link to. 

### Returns

Returns a success message and an email will be sent to user with the magic link. Once user clicks on magic link goodcop will redirect to the product callback. If no email was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `Email is missing`


## SignIn using phonenumber

> Definition

```
POST  https://dev.goodcop.com/v1/user/signin/phone

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signin/phone"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

Creates an one time password for user verfication.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signin/phone`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
phoneNumber | required | string | Phone number to send otp 

### Returns

Returns a success message and an one time password will be sent to user to verify.If no email was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `Phone number is missing`
3.  `SMS sending error`

## Verfiy phonenumber

> Definition

```
POST  https://dev.goodcop.com/v1/user/signin/phone/verify

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/signin/phone/verify"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

Creates a new user object after verifying the otp.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/signin/phone/verify`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
phoneNumber | required | string | Phone number of the user 
otp | required | string | otp sent to user mobile

### Returns

Returns a user object if correct otp and phoneNumber was provided. The returned object will have user details with phone number and token. If no otp or phoneNumber was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `Phone number or OTP missing`

## Login

> Definition

```
POST  https://dev.goodcop.com/v1/user/login

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/login"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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
    "devicetokens": [
        {
            "token": "R4QzpVxvYuS03W-ap54J6tgDj86pkGNQ60szc_7PbR1D4jbhJk1cFmJAjOUPpoew5vSV_prXFsRUxKeuY-GLxg==",
            "deviceid": "test_56789657567"
        }
    ],
    "verified": false,
    "createdAt": "2018-03-22T14:13:19.654089+05:30",
    "updatedAt": "2018-03-22T14:13:19.654091+05:30"
}

```

LogIn the user.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/login`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | The email address of the user
password | required | string | The password of the user

### Returns

Returns a user object if correct email and password was provided. The returned object will have information about the rules, groups, metadata. If no email or password was provided, incorrect passowrd/email validation or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `Either email or password is missing`
3.  `Password must be atleast 7 characters long`
3.  `No Password,Please Set a password after signing in using magic link`

## Change password

> Definition

```
POST  https://dev.goodcop.com/v1/user/passwordChange

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/passwordChange"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

`POST https://dev.goodcop.com/v1/user/passwordChange`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
oldapassword | required | string | The old password of the user. 
newapassword | required | string | The new password to set. 

### Returns

Returns a success message. If no user token was provided, incorrect passwords or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `user not found`
3.  `Wrong Old Password`
4.  `Password must be atleast 7 characters long`


## Get user by Id

> Definition

```
GET  https://dev.goodcop.com/v1/user/{userID}

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": null,
    "groups": null,
    "meta": "",
    "devicetokens": [
        {
            "token": "u82e715S5xutCVdu-EIL4A63g7Z_uFNLYAnrIjQbO10iYFiwkPher5BVqoin8hcHeFifSpcQ6x3hAx1CPigNbA==",
            "deviceid": "test_56789657567"
        }
    ],
    "verified": true,
    "createdAt": "0001-01-01T05:21:10+05:21",
    "updatedAt": "0001-01-01T05:21:10+05:21"
}
```

Retrieves the details of an existing user. You need only supply the unique user identifier that was returned upon user creation.

### HTTPS Request

`POST https://dev.goodcop.com/v1/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns a user object if a valid identifier was provided. If invalide user id was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `User not found`

## Get user By email


> Definition

```
GET  https://dev.goodcop.com/v1/getUser/{email}

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/getUser/test@mail.com"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json
{
    "userId": "test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
    "email": "test@mail.com",
    "rules": null,
    "groups": null,
    "meta": "",
    "devicetokens": [
        {
            "token": "e_aMotSZFW0A9QiXWE0N2dkDIiLUBLHLrS6hAQyhD98Py11RAb4_YKjNijvaX4m5qWN8JwBhhi48iecFF38DmA==",
            "deviceid": ""
        }
    ],
    "verified": true,
    "createdAt": "2018-03-22T11:25:29.803822+05:30",
    "updatedAt": "2018-03-22T11:26:29.536281+05:30"
}
```

Retrieves the details of an existing user. You need only supply the unique email of the user.

### HTTPS Request

`GET https://dev.goodcop.com/v1/getUser/{email}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
email | required | string | Valid email address 

### Returns

Returns a user object if a valid identifier was provided. If invalid email was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `Email is not valid`

## List all users

> Definition

```
GET  https://dev.goodcop.com/v1/user

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
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
            "devicetokens": [
                    {
                        "token": "TVzm6SDRY5i5lpXgrsNYxok9zgJODJsA7VB15yl2qvUeTG_n3HYmEHaYwt73K-1vGpsUTV18wssDyEWGHdInPw==",
                        "deviceid": ""
                    }
                ],
            "verified": false,
            "createdAt": "0001-01-01T05:21:10+05:21",
            "updatedAt": "2018-03-22T12:08:02.07777+05:30"
        },
        {
              "userId": "test1_oio4205c7-4139-4e14-a0d0-c5932ad99e9a",
              "email": "test1@mail.com",
              "rules": null,
              "groups": null,
              "meta": "",
               "devicetokens": [
                    {
                        "token": "TVzm6SDRY5i5lpXgrsNYxok9zgJODJsA7VB15yl2qvUeTG_n3HYmEHaYwt73K-1vGpsUTV18wssDyEWGHdInPw==",
                        "deviceid": "13ACFCFB-40F6-4823-B8FC-8CA3D3A5DEDE"
                    }
                ],
              "verified": true,
              "createdAt": "0001-01-01T05:21:10+05:21",
              "updatedAt": "2018-03-22T12:08:02.07777+05:30"
        },
    ]
}
```
Retrieves the detailed list of all product users. The users are returned in descending order of creation.

### HTTPS Request

`GET https://dev.goodcop.com/v1/user`

### Returns

Returns a list of user objects. If any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`

## Delete user by Id

> Definition

```
DELETE  https://dev.goodcop.com/v1/user/{userID}

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response

```json
{
    "message": "User deleted successfully"
}

```

Deletes a user from the product. The user is not deleted permanently.

### HTTPS Request

`DELETE https://dev.goodcop.com/v1/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns a message on success. If the user ID does not exist an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `User not found`

## Get Group Details By ID

> Definition

```
GET  https://dev.goodcop.com/v1/user/{userID}/groups

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/groups"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

Retrieves the group details provided the user ID.

### HTTPS Request

`GET https://dev.goodcop.com/v1/user/{userID}/groups`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns an array of group objects. If invalid user ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key`
2.  `User not found`


## Get User Meta By ID

> Definition

```
GET  https://dev.goodcop.com/v1/user/{userID}/meta

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/meta"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
```

> Example Response

```json
{
    "meta": "storing test meta info",
}
```
Retrieves the meta details provided the user ID.

### HTTPS Request

`GET https://dev.goodcop.com/v1/user/{userID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 


### Returns

Returns meta string. If invalid user ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  `Invalid product API key` <aside style="background:#5bc0de;">400</aside> 
2.  `User not found`



## Update User Meta By ID

Provide the unique user ID and Goodcop will return the meta details.

> Definition

```
PUT  https://dev.goodcop.com/v1/user/{userID}/meta

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

`PUT https://dev.goodcop.com/v1/user/{userID}/meta`

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
GET  https://dev.goodcop.com/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

`GET https://dev.goodcop.com/v1/user/{userID}/rule`

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
PUT  https://dev.goodcop.com/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/rule"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

`PUT https://dev.goodcop.com/v1/user/{userID}/rule`

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
DELETE  https://dev.goodcop.com/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/rule"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

`DELETE https://dev.goodcop.com/v1/user/{userID}/rule`

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
GET  https://dev.goodcop.com/v1/user/{userID}/groups

```
> Example Request

```shell
curl "https://dev.goodcop.com/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/groups"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Token: test_56789657567"
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

`GET https://dev.goodcop.com/v1/user/{userID}/groups`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
userID | required | string | Valid user identifier 

### Returns

Returns array of group details with a valid authorization key and a valid identifier was provided, and returns an error otherwise.