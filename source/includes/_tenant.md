# Tenant

The API allows you to create, delete, and update tenant. The api gives ability to set authorization level privileges using the rules object and metadata storage. You can also set protected information in the secrets api for tenant.

<aside style="background:#5bc0de;">
The x-api-key header must be provided to request the tenant api's.
</aside>

## Create Tenant


> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant"
  -X  POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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
    "secrets": "secrets",
    "createdAt": "2018-03-21T17:03:16.024791+05:30",
    "updatedAt": "2018-03-21T17:03:16.024793+05:30"
}
```

Creates a new tenant object.


### HTTPS Request

<code style="background:#4CAF50;">POST</code> <code style="background:#E8F5E9;">https://[GOODCOP_URL]/v1/tenant</code>

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | name of the tenant
apiID | optional | integer |  apiID of the tenant
rules | optional | array | rules of tenant
meta | optional | string | meta information of the tenant 
secrets | optional | string | secrets of tenant  


### Returns

Returns a api object. The returned object will have information about the rules, description, metadata and api key that is necessary for using tenant module. If no api name was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant Already Exist with the name provided`
4.  <code style="background:#FFC107;"> 400 </code> `Tenant name is required`
5.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get Tenant By ID


> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}"
  -X  GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" 
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
    "secrets": ""
}

```

Retrieves the details of an existing tenant. You need only supply the unique tenant identifier that was returned upon tenant creation.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/tenant/{tenantID}</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns a tenant object if a valid identifier was provided. If invalid tenant ID was provided or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get All Tenants


> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant"
  -X  GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Retrieves the detailed list of all product tenants.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/tenant`</code>


### Returns

Returns a list of tenant objects. If any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key`
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

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
  -H "Content-Type: application/json"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Tenant has been deleted for tenantID - 5996636694118400"
}

```

Deletes a tenant from the product permanently.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/tenant/{tenantID}`


### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns a message on success. If the tenant ID does not exist or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


## Get Rule By ID


> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Retrieves the details of all rules for a tenant.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/tenant/{tenantID}/rule</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns the list of tenant rules. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


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
  -H "Content-Type: application/json"
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

Updates the rules by setting the value of the body parameter passed.

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

Returns updated rules for the tenant. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FFC107;"> 400 </code> `Not Acceptable - You requested a wrong rule format`
5.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`


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

Deletes the rules from the tenant.

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

Returns tenant object with updated rules. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FFC107;"> 400 </code> `Not Acceptable - You requested a wrong rule format`
5.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

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
  -H "Content-Type: application/json"
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

Updates the secrets by setting the value of the body parameter passed. The secret information is stored in protected format.

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

Returns updated secrets in the tenant. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FFC107;"> 400 </code> `secrets should be stringified object`
5.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get Secret By ID


> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret"
  -X "GET"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
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

Retrieves the secret information for the tenant. 

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/tenant/{tenantID}/secret</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns the secrets stored with the tenant. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

## Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FFC107;"> 400 </code> `Not Acceptable - You requested a wrong secrets format`
5.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

## Get Meta By ID

> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta"
  -X "GET"
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json"
  -H 'x-api-key: test_MLd587_Hi3TrTwfLNRg8mKiUwDlM7Z5VuODE9KhM8=' \
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "meta": "tenant meta"
}

```

Retrieves the meta details provided the tenant ID.

### HTTPS Request

<code style="background:#2196F3;">GET</code> <code style="background:#E3F2FD;">https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta</code>

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns meta string. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

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
  -H "Content-Type: application/json"
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

Updates the meta by setting the value of the body parameter passed.

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

Returns updated tenant object with updated string. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`

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
  -H "Content-Type: application/json"
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

Replaces the meta with empty string.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/tenant/{tenantID}/meta`


### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
tenantID | required | string | Valid tenant identifier


### Returns

Returns tenant object with no metadata. If invalid tenant ID or any other backend failures an appropriate error message will be returned with an error code associated with it.

### Error Messages

1.  <code style="background:#FF7043;"> 401 </code> `Invalid product API key` 
2.  <code style="background:#FF7043;"> 401 </code> `Authorization Error. Kindly provide correct API key`
3.  <code style="background:#FFC107;"> 400 </code> `Tenant does not exist for given api ID`
4.  <code style="background:#FF0000;"> 500 </code> `We had a problem with our server. Try again later.`