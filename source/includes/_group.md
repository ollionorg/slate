# Group

The API allows you to create, delete, and update groups. You can retrieve a list of all your users associated with a group. Also the api gives ability to set authorization level privileges using the rules object and metadata storage.


## Create Group

> Definition

```
<code style="background:#01579B;"> POST</code>  https://[GOODCOP_URL]/v1/group

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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
    "productId": 5750501782061056,
    "createdAt": "2018-03-22T16:54:51.578986+05:30",
    "updatedAt": "2018-03-22T16:54:51.578987+05:30"
}
```

Creates a new group object.

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

Returns a group object. The returned object will have information about the rules, description, metadata. If no group name was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group name is required`


## Get Group By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/group/{groupID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5707274949492736"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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
    "productId": 5750501782061056,
    "createdAt": "2018-03-22T16:54:51.578986+05:30",
    "updatedAt": "2018-03-22T16:54:51.578987+05:30"
}

```
Retrieves the details of an existing group. You need only supply the unique group identifier that was returned upon group creation.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/group/{groupID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns a group object if a valid identifier was provided. If invalid group id was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group does not exist for given groupID`

## List Groups

> Definition

```
GET  https://[GOODCOP_URL]/v1/group

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Retrieves the detailed list of all product groups. The groups are returned in descending order of creation.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/group`

### Returns

Returns a list of group objects. If any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 

## Delete Group By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5707274949492736"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Group has been deleted for groupID - 5707274949492736"
}
```

Deletes a group from the product permanently.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns a message on success. If the group ID does not exist or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group does not exist for given groupID`

## Delete Multiple Group

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
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Groups Deleted Successfully"
}
```

Deletes multiple groups from the product permanently.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupIDs | array | integer | Array of Valid group identifiers

### Returns

Returns a message on success. If the group ID does not exist or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group does not exist for given groupID`


## Add Multiple Users to Group By ID

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

Adds multiple users to a group.

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

Returns an array of users which were succesfully added to the group. If the group ID does not exist, user IDs are invalid or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Users not found`
3.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`


## Add Single User to Group By Email

> Definition

```
PUT  https://[GOODCOP_URL]/v1/group/{groupID}/userEmail

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5707274949492736/userEmail"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Adds a single user to a group by email address.

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

Returns an array of users which were succesfully added to the group. If the group ID does not exist, user IDs are invalid or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Users not found`
3.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`


## Get User for Group By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/user/test_a660-9242-4521-b614-e46ffead2b2b"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Retrieves the details of an user in a group. You need only supply the unique user and group identifier.

### HTTPS Request

`GET  https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 
userID | required | string | Valid user identifier 

### Returns

Returns a user object if a valid identifiers was provided. If invalid user ID or group ID was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Users not found`
3.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`


## Get All Users for Group By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/group/{groupID}/user

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/user"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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
            "devicetokens": [
                    {
                        "token": "e_aMotSZFW0A9QiXWE0N2dkDIiLUBLHLrS6hAQyhD98Py11RAb4_YKjNijvaX4m5qWN8JwBhhi48iecFF38DmA==",
                        "deviceid": "13ACFCFB-40F6-4823-B8FC-8CA3D3A5DEDE"
                    }
                ],
              "verified": true,
              "createdAt": "0001-01-01T05:21:10+05:21",
              "updatedAt": "2018-03-22T12:08:02.07777+05:30"
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
           "devicetokens": [
                    {
                        "token": "TVzm6SDRY5i5lpXgrsNYxok9zgJODJsA7VB15yl2qvUeTG_n3HYmEHaYwt73K-1vGpsUTV18wssDyEWGHdInPw==",
                        "deviceid": ""
                    }
                ],
              "verified": true,
              "createdAt": "0001-01-01T05:21:10+05:21",
              "updatedAt": "2018-03-22T12:08:02.07777+05:30"
        }
    ]
}

```

Retrieves the details of all users in a group.

### HTTPS Request

`GET  https://[GOODCOP_URL]/v1/group/{groupID}/user`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 


### Returns

Returns a list of user objects. If any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 

## Delete User from Group By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/user/test_a660-9242-4521-b614-e46ffead2b2b"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Group deleted successfully"
}
```

Removes the a single user from a group.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}/user/{userID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 
userID | required | string | Valid user identifier 

### Returns

Returns a success message on removal of user from the group. If invalid user ID, group ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Users not found`
3.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`

## Get Group Meta By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "meta": "test meta"

```

Retrieves the meta details provided the group ID.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns meta string. If invalid group ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`


## Update Group Meta By ID

> Definition

```
PUT  https://[GOODCOP_URL]/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Updates the meta by setting the value of the body parameter passed.

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

Returns updated meta string. If invalid group ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`


## Delete Group Meta By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Replaces the meta with empty string.

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

Returns group object with no metadata. If invalid group ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`


## Get Group Rules By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/group/{groupID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Retrieves the details of all rules in a group.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/group/{groupID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns the list of group rules. If invalid group ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`

## Update Group Rules By ID

> Definition

```
PUT  https://[GOODCOP_URL]/v1/user/{userID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/rule"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Updates the rules by setting the value of the body parameter passed.

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

Returns updated rules in the group. If invalid user ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`
3.  <code style="background:#FFC107;"> 400 </code> `Not Acceptable - You requested a wrong rule format`

## Delete Group Rules By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/group/{groupID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/group/5717800035287040/rule"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" 
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

Deletes the rules from the group.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/group/{groupID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
groupID | required | string | Valid group identifier 

### Returns

Returns updated rules. If invalid group ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFC107;"> 400 </code> `Group id is not valid`
3.  <code style="background:#FFC107;"> 400 </code> `Not Acceptable - You requested a wrong rule format`