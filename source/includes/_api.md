# Api

The API allows you to create, delete, and update api. The api gives ability to set authorization level privileges using the rules object and metadata storage.

## Create Api

> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
  -d '{
	"name":"api test",
	"description":"this is test api",
	"rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta":"test api",
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json

{
    "id": 5643625413214208,
    "name": "api test",
    "description": "this is test api",
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta": "test api",
    "apiKeys": [
        {
            "name": "default",
            "value": "asZ7nYKajsIl8RqtYYK-oyS2MC_6EKMYXMCDq0J7FfQ="
        }
    ],
    "productId": 6308443803615232,
    "createdAt": "2018-03-21T17:03:16.024791+05:30",
    "updatedAt": "2018-03-21T17:03:16.024793+05:30"
}

```

Creates a new api object.

### HTTPS Request

<code style="background:#4CAF50;">POST</code> <code style="background:#E8F5E9;">https://[GOODCOP_URL]/v1/api</code>

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | name of the api
description | optional | string |  description of the api
rules | optional | array | rules of api
meta | optional | string | meta information of the api 


### Returns

Returns a api object. The returned object will have information about the rules, description, metadata and api key that is necessary for using tenant module. If no api name was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API Already Exist with the name provided`
3.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `Api name is required`
4.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get Api By ID

> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
        "id": 5643625413214208,
        "name": "api test",
        "description": "this is test api",
        "rules": [
            {
                "verb": "GET",
                "path": "/organizations/5746055551385600/*",
                "effect": true
            }
        ],
        "meta": "test api",
        "apiKeys": [
            {
                "name": "default",
                "value": "asZ7nYKajsIl8RqtYYK-oyS2MC_6EKMYXMCDq0J7FfQ="
            }
        ],
        "productId": 6308443803615232
    }

```
Retrieves the details of an existing api. You need only supply the unique api identifier that was returned upon api creation.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/api/{apiID}</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns a api object if a valid identifier was provided. If invalid api ID was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get All Apis

> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "Apis": [
        {
            "id": 5643625413214208,
            "name": "api test",
            "description": "this is test api",
            "rules": [
                {
                    "verb": "GET",
                    "path": "/organizations/5746055551385600/*",
                    "effect": true
                }
            ],
            "meta": "test api",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "asZ7nYKajsIl8RqtYYK-oyS2MC_6EKMYXMCDq0J7FfQ="
                }
            ],
            "productId": 6308443803615232
        },
        {
            "id": 5765033938124800,
            "name": "api test1",
            "description": "this is test api",
            "rules": [
                {
                    "verb": "GET",
                    "path": "/organizations/5746055551385600/*",
                    "effect": true
                }
            ],
            "meta": "test api",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "erFaJxbDbHp_J_WlpqpFXzH_OsUiudCNRPYm_bS_V7w="
                }
            ],
            "productId": 6308443803615232
        },
        {
            "id": 5916827746041856,
            "name": "test api",
            "description": "",
            "rules": [
                {
                    "verb": "GET",
                    "path": "/organizations/5746055551385600/*",
                    "effect": true
                }
            ],
            "meta": "api meta",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "o_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8="
                }
            ],
            "productId": 6308443803615232
        }
    ]
}

```

Retrieves the detailed list of all product apis.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/api</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier

### Returns

Returns a list of api objects. If any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key`
2.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Delete Api By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/api/{apiID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Api has been deleted for apiID - 5765033938124800"
}

```
Deletes a api from the product permanently.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/api/{apiID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns a message on success. If the api ID does not exist or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Get rule By ID

> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "Rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ]
}

```

Retrieves the details of all rules in a api.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/api/{apiID}/rule</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns the list of api rules. If invalid api ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Update rule By ID


> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}/rule"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
  -d '[
        {
            "verb": "PUT",
            "path": "/organizations/5162157834502144/*",
            "effect": true
        },
        {
            "verb": "POST",
            "path": "/organizations/5162157834502144/*",
            "effect": true
        }
    ]'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        },
        {
            "verb": "PUT",
            "path": "/organizations/5162157834502144/*",
            "effect": true
        },
        {
            "verb": "POST",
            "path": "/organizations/5162157834502144/*",
            "effect": true
        }
    ]
}

```

Updates the rules by setting the value of the body parameter passed.

### HTTPS Request

<code style="background:#FFC107;">GET</code> <code style="background:#FFF8E1;">https://[GOODCOP_URL]/v1/api/{apiID}/rule</code>

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier

### Returns

Returns updated rules in the api. If invalid api ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `Not Acceptable - You requested a wrong rule format`
4.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Delete rule By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/api/{apiID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}/rule"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
  -d '[
        {
            "verb": "PUT",
            "path": "/organizations/5162157834502144/*",
            "effect": true
        },
        {
            "verb": "POST",
            "path": "/organizations/5162157834502144/*",
            "effect": true
        }
    ]'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5643625413214208,
    "name": "api test",
    "description": "this is test api",
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta": "test api",
    "apiKeys": [
        {
            "name": "default",
            "value": "asZ7nYKajsIl8RqtYYK-oyS2MC_6EKMYXMCDq0J7FfQ="
        }
    ],
    "productId": 6308443803615232
}
```

Deletes the rules from the api.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/api/{apiID}/rule`


### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be deleted 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns updated rules. If invalid api ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `Not Acceptable - You requested a wrong rule format`
4.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get Meta By ID

> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}/meta"
  -X  GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "meta": "api meta"
}

```

Retrieves the meta details provided the group ID.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/api/{apiID}/meta</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns meta string. If invalid api ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Update Meta By ID


> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"meta":"update tenant meta"
}'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5643625413214208,
    "name": "api test",
    "description": "this is test api",
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta": "updated api meta",
    "apiKeys": [
        {
            "name": "default",
            "value": "asZ7nYKajsIl8RqtYYK-oyS2MC_6EKMYXMCDq0J7FfQ="
        }
    ],
    "productId": 6308443803615232
}
```

Updates the meta by setting the value of the body parameter passed.

### HTTPS Request

<code style="background:#FFC107;">GET</code> <code style="background:#FFF8E1;">https://[GOODCOP_URL]/v1/api/{apiID}/meta</code>

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string  | meta to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


Returns updated meta string. If invalid api ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Delete Meta By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/api/{apiID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/api/{apiID}/meta"
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
    "id": 5643625413214208,
    "name": "api test",
    "description": "this is test api",
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta": "",
    "apiKeys": [
        {
            "name": "default",
            "value": "asZ7nYKajsIl8RqtYYK-oyS2MC_6EKMYXMCDq0J7FfQ="
        }
    ],
    "productId": 6308443803615232
}
```

Replaces the meta with empty string.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/api/{apiID}/meta`


### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns api object with no metadata. If invalid api ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FFFFFF;color:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FFFFFF;color:#FFC107;"> 400 </code> `API does not exist for given api ID`
3.  <code style="background:#FFFFFF;color:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`