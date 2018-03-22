# Tenant

## Create Tenant

> Definition

```
POST  https://[GOODCOP_URL]/v1/tenant

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant"
  -X "POST"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
  -d '{
	"name":"test tenant",
	"apiId":5916827746041856,
	"rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta":"tenant meta",
    "secrets":"secrets"
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5996636694118400,
    "name": "test tenant",
    "apiId": 5916827746041856,
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta": "tenant meta",
    "secrets": "secrets"
}
```

Creates a tenant object provided the request body and returns the group object.

<aside style="background:#5bc0de;">
The x-api-key header must be provided to create a tenant.
</aside>

### HTTPS Request

`POST https://[GOODCOP_URL]/v1/tenant`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | name of the tenant
apiID | optional | integer |  apiID of the tenant
rules | optional | array | rules of tenant
meta | optional | string | meta information of the tenant 
secrets | optional | string | secrets of tenant  


### Returns

Returns new tenant object if a valid authorization key and api key was provided, and returns an error otherwise.

## Get Tenant By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/tenant/{tenantID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}"
  -X "GET"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5996636694118400,
    "name": "test tenant",
    "apiId": 5916827746041856,
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta": "tenant meta",
    "secrets": "secrets"
}

```

Retrieves the details of a tenant. Provide the unique tenant ID and Goodcop will return the corresponding user information.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/tenant/{tenantID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns tenant details if a valid authorization key, api key and valid indentifier was provided, and returns an error otherwise.

## Get All Tenants

> Definition

```
GET  https://[GOODCOP_URL]/v1/tenant

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant"
  -X "GET"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "tenants": [
        {
            "id": 5996636694118400,
            "name": "test tenant",
            "apiId": 5916827746041856,
            "rules": [
                {
                    "verb": "GET",
                    "path": "/organizations/5746055551385600/*",
                    "effect": true
                }
            ],
            "meta": "tenant meta",
            "secrets": "secrets"
        }
    ]
}

```

Retrieves the details of a all tenants for a particular api.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/tenant`


### Returns

Returns array of tenants if a valid authorization key, api key was provided, and returns an error otherwise.

## Delete Tenant By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/tenant/{tenantID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Tenant has been deleted for tenantID - 5996636694118400"
}

```

Deletes the tenant.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/tenant/{tenantID}`


### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns string message if a valid authorization key, api key was provided, and returns an error otherwise.

## Get Rule By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
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

Provide the unique tenant ID and Goodcop will return the list of all rules.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns rules object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Update Rule By ID

> Definition

```
PUT  https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
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

Retrives all rules of a tenants for a particular api.

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be deleted 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns array of rules if a valid authorization key, api key was provided, and returns an error otherwise.


## Delete Rule By ID


> Definition

```
DELETE  https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
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
    "id": 5996636694118400,
    "name": "test tenant",
    "apiId": 5916827746041856,
    "rules": [
        {
            "verb": "GET",
            "path": "/organizations/5746055551385600/*",
            "effect": true
        }
    ],
    "meta": "",
    "secrets": "{\"email\":\"mail@gmail.com\"}"
}
```

Deletes the rules associated with the tenant. 

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule`


### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be deleted 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns tenant object with deleted rules info if a valid authorization key, api key was provided, and returns an error otherwise.

## Update Secret By ID

> Definition

```
PUT  https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
  -d '{
	"secrets":"{\"email\":\"mail@gmail.com\"}"
}'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5996636694118400,
    "name": "test api",
    "apiId": 5916827746041856,
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
    ],
    "meta": "api meta",
    "secrets": "{\"email\":\"mail@gmail.com\"}"
}
```

Retrives all rules of a tenants for a particular api.

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
secrets | required | string object | secrets to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns tenant object with updated secret info if a valid authorization key, api key was provided, and returns an error otherwise.

## Get Secret By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret"
  -X "GET"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "secrets": {
        "email": "guggs24@gmail.com"
    }
}

```

Provide the unique tenant ID and Goodcop will return the secret.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns secrets if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get Meta By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta"
  -X "GET"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "meta": "tenant meta"
}

```

Provide the unique tenant ID and Goodcop will return the meta information.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns string meta if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Meta By ID


> Definition

```
PUT  https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
  -d '{
	"meta":"update tenant meta"
}'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5996636694118400,
    "name": "test tenant",
    "apiId": 5916827746041856,
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
    ],
    "meta": "updated tenant meta",
    "secrets": "{\"email\":\"mail@gmail.com\"}"
}
```

Updated meta details of the tenant.

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
meta | required | string  | meta to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns tenant object with updated meta info if a valid authorization key, api key was provided, and returns an error otherwise.

## Delete Meta By ID 


> Definition

```
DELETE  https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
  -d '{
	    "meta":""
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5996636694118400,
    "name": "test tenant",
    "apiId": 5916827746041856,
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
    ],
    "meta": "",
    "secrets": "{\"email\":\"mail@gmail.com\"}"
}
```

Deletes the meta associated with the tenant. 

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta`


### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns tenant object with deleted meta info if a valid authorization key, api key was provided, and returns an error otherwise.
