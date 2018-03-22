# Group

## Create Group

> Definition

```
POST  https://[GOODCOP_URL]/v1/group

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
        "name":"test_group",
        "rules":[
            {"path":"thrifty/billing","verb":"GET","effect":true}
        ]
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`POST https://[GOODCOP_URL]/v1/group`

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
GET  https://[GOODCOP_URL]/v1/group/{groupID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5707274949492736"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`GET https://[GOODCOP_URL]/v1/group/{groupID}`

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
GET  https://[GOODCOP_URL]/v1/group

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`GET https://[GOODCOP_URL]/v1/group`

### Returns

Returns list of group objects if a valid authorization key was provided, and returns an error otherwise.

## Delete Group By ID

Provide the unique group ID and Goodcop will return the message for successful deletion of group.

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5707274949492736"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Group has been deleted for groupID - 5707274949492736"
}
```

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}`

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
DELETE  https://[GOODCOP_URL]/v1/group

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group"
  -X DELETE
  -d '[5717800035287040,5717800035287766]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Groups Deleted Successfully"
}
```

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group`

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
PUT  https://[GOODCOP_URL]/v1/group/{groupID}/user

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5707274949492736/user"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{ 
      "users":[
                    "01e097a1-fedd-466f-96c9-3eaee6cc7f1f",
                    "022fa660-9242-4521-b614-e46ffead2b2b"
              ]
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`PUT https://[GOODCOP_URL]/v1/group/{groupID}/users`

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
PUT  https://[GOODCOP_URL]/v1/group/{groupID}/userEmail

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5707274949492736/userEmail"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{ 
	    "email":"test@mail.com"
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "user": "test_a660-9242-4521-b614-e46ffead2b2b"
}

```

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/group/{groupID}/userEmail`

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
GET  https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/user/test_a660-9242-4521-b614-e46ffead2b2b"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`GET  https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}`

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
GET  https://[GOODCOP_URL]/v1/group/{groupID}/user

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/user"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`GET  https://[GOODCOP_URL]/v1/group/{groupID}/user`

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
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/user/test_a660-9242-4521-b614-e46ffead2b2b"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Group deleted successfully"
}
```

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}`

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
GET  https://[GOODCOP_URL]/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "meta": "test meta"

```

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}/meta`

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
PUT  https://[GOODCOP_URL]/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	    "meta":"update test meta"
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "meta": "update test meta"
}

```

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/group/{groupID}/meta`

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
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	    "meta":""
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}/meta`

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
GET  https://[GOODCOP_URL]/v1/group/{groupID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`GET https://[GOODCOP_URL]/v1/group/{groupID}/rule`

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
PUT  https://[GOODCOP_URL]/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/rule"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '[{
            "verb": "DELETE",
            "path": "/credentials/5687539843203072",
            "effect": true
    }]'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`PUT https://[GOODCOP_URL]/v1/group/{groupID}/rule`

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
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/rule"
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

> Example Response <code style="background:#4CAF50;"> 200</code>

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

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns updated rules object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.
