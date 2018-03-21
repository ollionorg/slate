# Organization

## Create Org

> Definition

```
POST  https://api.goodcop.com/v1/org

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/org"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"name":"testorg",
	"meta":"test meta",
	"contactdetails":"+918879777777"
}'
```

> Example Response

```json
{
    "id": 5642425909379072,
    "name": "testorg",
    "meta": "test meta",
    "contactDetails": "+918879777777",
    "CreatedAt": "2018-03-21T17:03:16.024791+05:30",
    "UpdatedAt": "2018-03-21T17:03:16.024793+05:30"
}

```

Creates a organization

### HTTPS Request

`POST https://api.goodcop.com/v1/org`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | name of the org
meta | optional | string |  metadata for org
contactDetails | optional | string | contact details to be stored for the org


### Returns

Returns new org object if a valid authorization key provided, and returns an error otherwise.

## List Org

> Definition

```
GET  https://api.goodcop.com/v1/org

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/org"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "Organizations": [
        {
            "id": 5649353691627520,
            "name": "test-org",
            "meta": "",
            "contactDetails": "",
            "CreatedAt": "2018-03-19T15:32:22.677154+05:30",
            "UpdatedAt": "2018-03-19T15:32:22.677154+05:30"
        },
        {
            "id": 5642425909379072,
            "name": "testorg",
            "meta": "test meta",
            "contactDetails": "+918879777777",
            "CreatedAt": "2018-03-21T17:03:16.024791+05:30",
            "UpdatedAt": "2018-03-21T17:03:16.024793+05:30"
        },
    ]
}
```
Goodcop will return the all organization information for the product.

### HTTPS Request

`GET https://api.goodcop.com/v1/org`

### Returns

Returns all organization details if a valid authorization key and returns an error otherwise.

## Get Org by ID

> Definition

```
GET  https://api.goodcop.com/v1/org/{orgID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/org/5642425909379072"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json


```
Goodcop will return the all api information for the product.

### HTTPS Request

`GET https://api.goodcop.com/v1/org/{orgID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier


### Returns

Returns org details if a valid authorization key, and valid indentifier was provided, and returns an error otherwise.

## Delete Org By ID

Provide the unique org ID and Goodcop will return the message for successful deletion of org.

> Definition

```
DELETE  https://api.goodcop.com/v1/org/{orgID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/org/6309146567639040"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "Org Deleted Successfully"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/org/{orgID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Org

Provide the unique org ID and Goodcop will return the organization details.

> Definition

```
PUT  https://api.goodcop.com/v1/org/{orgID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/5642425909379072"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"contactdetails":"+91877777776666"
    }'
```

> Example Response

```json
{
    "id": 5642425909379072,
    "name": "testorg",
    "meta": "test meta",
    "contactDetails": "+91877777776666",
    "CreatedAt": "2018-03-21T17:03:16.024791+05:30",
    "UpdatedAt": "2018-03-21T17:16:10.013299+05:30"
}

```

### HTTPS Request

`PUT https://api.goodcop.com/v1/org/{orgID}`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
contactdetails | required | string | contactdetails to be updated for the org

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns org object with updated contact details if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get Org Meta By ID

Provide the unique org ID and Goodcop will return the meta details.

> Definition

```
GET  https://api.goodcop.com/v1/org/{orgID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/user/5642425909379072/meta"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "meta": "test meta"
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/org/{orgID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns meta information if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Org Meta By ID

Provide the unique org ID and Goodcop will return the meta details.

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
	"meta":"updated test meta"
    }'
```

> Example Response

```json
{
    "message": "meta updated successfully"
}

```

### HTTPS Request

`PUT https://api.goodcop.com/v1/org/{orgID}/meta`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string | Metadata to be updated for the org

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns string message of updation if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Org Meta By ID

Provide the unique org ID and Goodcop will delete the meta string.

> Definition

```
DELETE  https://api.goodcop.com/v1/org/{orgID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/product/5642425909379072/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: api" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "meta deleted successfully"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/org/{orgID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns success message string if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Add Users to Org

> Definition

```
POST  https://api.goodcop.com/v1/org/{orgID}/users

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/org/5642425909379072/users"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"users":["0ef3011b-b228-4771-bad5-bd7c0ebd70d8","3fd58316-6f6d-4c1b-9eb7-2678fe886b4d"]
}'
```

> Example Response

```json
{
    "message": "Users added to organizations"
}

```

Creates a organization

### HTTPS Request

`POST https://api.goodcop.com/v1/org/{orgID}/users`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
users | required | array | users ids


### Returns

Returns success message string if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get Org Users By ID

Provide the unique org ID and Goodcop will return the users details.

> Definition

```
GET  https://api.goodcop.com/v1/org/{orgID}/users

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/org/5642425909379072/users"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "response": "to be updated",
}
```

### HTTPS Request

`GET https://api.goodcop.com/v1/org/{orgID}/users`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
orgID | required | string | Valid org identifier 

### Returns

Returns users array associated with the org if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Remove Users from Org By ID

Provide the unique array of user IDs and Goodcop will return the message for successful deletion of users from org.

> Definition

```
DELETE  https://api.goodcop.com/v1/org/{orgID}/users

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/org/5642425909379072/users"
  -X DELETE
  -d '[5717800035287040,5717800035287766]'
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "Users deleted from organizations"
}
```

### HTTPS Request

`DELETE https://api.goodcop.com/v1/org/{orgID}/users`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
usersIDs | array | integer | Array of Valid user identifiers

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.
