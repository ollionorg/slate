# Organization

The API allows you to create, delete, and update an prganization. The api gives ability to store metadata, add/remove multiple users
from the organization.

## Create Org

> Definition

```
POST  https://[GOODCOP_URL]/v1/org

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/org"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
  -d '{
	"name":"testorg",
	"meta":"test meta",
	"contactdetails":"customer_detail_in_string"
}'
```

> Example Response <code style="background:#4CAF50;"> 201</code>

```json
{
    "id": 12345668787989,
    "name": "testorg",
    "meta": "test meta",
    "contactDetails": "customer_detail_in_string",
    "createdAt": "2018-03-21T17:03:16.024791+05:30",
    "updatedAt": "2018-03-21T17:03:16.024793+05:30"
}

```

Creates a new organization object.

### HTTPS Request

`POST https://[GOODCOP_URL]/v1/org`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | name of the org
meta | optional | string |  metadata for org
contactDetails | optional | string | contact details to be stored for the org


### Returns

Returns new org object if a valid authorization key provided, and returns an error otherwise, If Organization already exist with the name provided, it will throw an error 

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FFC107;"> 404 </code> `Name is required field`
3.  <code style="background:#FF0000;"> 500 </code> `Organization Already Exist with the name provided`
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## List Orgs

> Definition

```
GET  https://[GOODCOP_URL]/v1/org

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/org"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;">200</code>

```json
{
    "orgs": [
        {
            "id": 12345668787989,
            "name": "testorg",
            "meta": "test meta",
            "contactDetails": "customer_detail_in_string",
            "createdAt": "2018-03-21T17:03:16.024791+05:30",
            "updatedAt": "2018-03-21T17:03:16.024793+05:30"
        },
        {
            "id": 56424259099072,
            "name": "testorg2",
            "meta": "",
            "contactDetails": "",
            "createdAt": "2018-03-21T17:03:18.024791+05:30",
            "updatedAt": "2018-03-21T17:03:18.024793+05:30"
        },
    ]
}
```

Retrieves the detailed list of all organization for the product.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/org`

### Returns

Returns a list of org objects. If any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get Org by ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/org/{orgID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/org/5642425909379072"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;">200</code>

```json
{ 
    "id": 12345668787989,
    "name": "testorg",
    "meta": "test meta",
    "contactDetails": "customer_detail_in_string",
    "createdAt": "2018-03-21T17:03:16.024791+05:30",
    "updatedAt": "2018-03-21T17:03:16.024793+05:30"
}

```
Retrieves the details of an existing org. You need only supply the unique org identifier that was returned upon org creation.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/org/{orgID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier


### Returns

Returns a org object if a valid identifier was provided. If invalid org ID was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.


### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Delete Org By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/org/{orgID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/org/6309146567639040"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;">200</code>

```json
{
    "message": "Org Deleted Successfully"
}
```
Deletes an org from the product permanently.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/org/{orgID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns a message on success. If the org ID does not exist or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Update Org


> Definition

```
PUT  https://[GOODCOP_URL]/v1/org/{orgID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/user/5642425909379072"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
  -d '{
	"contactdetails":"+91877777776666"
    }'
```

> Example Response  <code style="background:#4CAF50;">201</code>

```json
{
    "id": 5642425909379072,
    "name": "testorg",
    "meta": "test meta",
    "contactDetails": "+91877777776666",
    "createdAt": "2018-03-21T17:03:16.024791+05:30",
    "updatedAt": "2018-03-21T17:16:10.013299+05:30"
}

```

Updates the org information by setting the value of the body parameter passed.

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/org/{orgID}`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
contactdetails | optional | string | contactdetails to be updated for the org

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns updated org object. If invalid org ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Get Org Meta By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/org/{orgID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/user/5642425909379072/meta"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;">200</code>

```json
{
    "meta": "test meta"
}
```

Retrieves the meta details provided the product ID.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/org/{orgID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns meta string. If invalid org ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Update Org Meta By ID

> Definition

```
PUT  https://[GOODCOP_URL]/v1/user/{userID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/user/test_oio4205c7-4139-4e14-a0d0-c5932ad99e9a/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"meta":"updated test meta"
    }'
```

> Example Response <code style="background:#4CAF50;">201</code>

```json
{
    "message": "meta updated successfully"
}

```

Updates the meta by setting the value of the body parameter passed.

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/org/{orgID}/meta`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string | Metadata to be updated for the org

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns updated meta string. If invalid org ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Meta should not empty, use \"deletemeta\" to delete it`
4.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
5.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Delete Org Meta By ID


> Definition

```
DELETE  https://[GOODCOP_URL]/v1/org/{orgID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5642425909379072/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: api" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;">200</code>

```json
{
    "message": "meta deleted successfully"
}
```

Replaces the meta with empty string.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/org/{orgID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns success message on succesfull deletion of meta. If invalid org ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Add Users to Org

> Definition

```
POST  https://[GOODCOP_URL]/v1/org/{orgID}/users

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/org/5642425909379072/users"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
  -d '{
	"users":["0ef3011b-b228-4771-bad5-bd7c0ebd70d8","3fd58316-6f6d-4c1b-9eb7-2678fe886b4d"]
}'
```

> Example Response <code style="background:#4CAF50;">201</code>

```json
{
    "message": "Users added to organizations"
}

```

Add multple users to an organization.

### HTTPS Request

`POST https://[GOODCOP_URL]/v1/org/{orgID}/users`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
users | required | array | Valid users identifier 
orgID | required | param | Valid org identifier 


### Returns

Returns string message on success. If the org ID does not exist, user IDs are invalid or any other backend failures an appropriate error message will be returned with an error code associated with it.


### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4.  <code style="background:#FF7043;"> 400 </code> `User not found` 
5.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Get Org Users By ID


> Definition

```
GET  https://[GOODCOP_URL]/v1/org/{orgID}/users

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/org/5642425909379072/users"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" 
```

> Example Response <code style="background:#4CAF50;">200</code>

```json
{
    "users": ["0ef3011b-b228-4771-bad5-bd7c0ebd70d8","3fd58316-6f6d-4c1b-9eb7-2678fe886b4d"]
}
```

Retrieves the user IDs for the organization. You need only supply the unique group identifier.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/org/{orgID}/users`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns a array of user IDs if a valid identifiers was provided. If invalid org ID was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable`
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4. <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.` 

## Remove Users from Org By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/org/{orgID}/users

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/org/5642425909379072/users"
  -X DELETE
  -d '[5717800035287040,5717800035287766]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"users":["0ef3011b-b228-4771-bad5-bd7c0ebd70d8","3fd58316-6f6d-4c1b-9eb7-2678fe886b4d"]
}'
```

> Example Response <code style="background:#4CAF50;">200</code>

```json
{
    "message": "Users deleted from organizations"
}
```

Removes the a multiple users from a group.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/org/{orgID}/users`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | integer | Org id to be passed in param

### Returns

Returns a success message on removal of users from the group. If invalid org ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Authorization error. Kindly provide product API key` 
2.  <code style="background:#FF7043;"> 400 </code> `Org id should be valid and parsable` 
3.  <code style="background:#FF7043;"> 400 </code> `Org not found` 
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`
