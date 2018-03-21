# Api

## Create Api

> Definition

```
POST  https://api.goodcop.com/v1/api

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
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

> Example Response

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

Creates a api object provided the request body and returns the api object.

### HTTPS Request

`POST https://api.goodcop.com/v1/api`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | name of the api
description | optional | string |  description of the api
rules | optional | array | rules of api
meta | optional | string | meta information of the api 


### Returns

Returns new api object if a valid authorization key and api key was provided, and returns an error otherwise.

## Get Api By ID

> Definition

```
GET  https://api.goodcop.com/v1/api/{apiID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

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
Provide the unique api ID and Goodcop will return the corresponding api information.

### HTTPS Request

`GET https://api.goodcop.com/v1/api/{apiID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns api details if a valid authorization key, api key and valid indentifier was provided, and returns an error otherwise.

## Get All Apis

> Definition

```
GET  https://api.goodcop.com/v1/api

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

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
Goodcop will return the all api information for the product.

### HTTPS Request

`GET https://api.goodcop.com/v1/api`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns all apis details if a valid authorization key, api key and valid indentifier was provided, and returns an error otherwise.

## Delete Api By ID

> Definition

```
DELETE  https://api.goodcop.com/v1/api/{apiID}

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "message": "Api has been deleted for apiID - 5765033938124800"
}

```
Provide the unique api ID and Goodcop will delete the api information.

### HTTPS Request

`DELETE https://api.goodcop.com/v1/api/{apiID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns a string message if a valid authorization key, api key and valid indentifier was provided, and returns an error otherwise.


## Get rule By ID

> Definition

```
GET  https://api.goodcop.com/v1/api/{apiID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

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

Provide the unique api ID and Goodcop will return the list of all rules.

### HTTPS Request

`GET https://api.goodcop.com/v1/api/{apiID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns rules object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update rule By ID

> Definition

```
PUT  https://api.goodcop.com/v1/api/{apiID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}/rule"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
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

> Example Response

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

Retrives all rules of a api.

### HTTPS Request

`PUT https://api.goodcop.com/v1/api/{apiID}/rule`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be deleted 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns array of rules if a valid authorization key and returns an error otherwise.


## Delete rule By ID

> Definition

```
DELETE  https://api.goodcop.com/v1/api/{apiID}/rule

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}/rule"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
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

> Example Response

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

Deletes the rules associated with the tenant. 

### HTTPS Request

`DELETE https://api.goodcop.com/v1/api/{apiID}/rule`


### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be deleted 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns api object with deleted rules info if a valid authorization key and returns an error otherwise.

## Get Meta By ID

> Definition

```
GET  https://api.goodcop.com/v1/api/{apiID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}/meta"
  -X  GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response

```json
{
    "meta": "api meta"
}

```

Provide the unique tenant ID and Goodcop will return the meta information.

### HTTPS Request

`GET https://api.goodcop.com/v1/api/{apiID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns string meta if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Meta By ID

> Definition

```
PUT  https://api.goodcop.com/v1/api/{apiID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"meta":"update tenant meta"
}'
```

> Example Response

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

Updated meta details of the api.

### HTTPS Request

`PUT https://api.goodcop.com/v1/api/{apiID}/meta`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string  | meta to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns api object with updated meta info if a valid authorization key and returns an error otherwise.

## Delete Meta By ID

> Definition

```
DELETE  https://api.goodcop.com/v1/api/{apiID}/meta

```
> Example Request

```shell
curl "https://api.goodcop.com/v1/api/{apiID}/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"meta":""
}'
```

> Example Response

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

Deletes the meta associated with the api. 

### HTTPS Request

`DELETE https://api.goodcop.com/v1/api/{apiID}/meta`


### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
apiID | required | string | Valid api identifier


### Returns

Returns api object with deleted meta info if a valid authorization key and returns an error otherwise.