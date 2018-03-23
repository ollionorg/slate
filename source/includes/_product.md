
# Product

## List Products

Retrieves the details of all products that has previously been created. 

<aside style="background:#f0ad4e;">
The Authorization token is a super secure token that is only accessible to administrators of Goodcop Api.
</aside>


> Definition

```
GET  https://[GOODCOP_URL]/v1/product

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "Products": [
        {
            "id": 5735995932672000,
            "name": "product_1",
            "description": "product_1",
            "authCallback": "https://requestb.in/1f4y9ho1",
            "apiRules": [
                {
                    "verb": "POST",
                    "path": "/product_1/billing",
                    "effect": false
                },
                {
                    "verb": "POST",
                    "path": "/product_1/billin",
                    "effect": true
                },
                {
                    "verb": "POST",
                    "path": "/dkd",
                    "effect": false
                }
            ],
            "apiMeta": "123",
            "userRules": null,
            "userMeta": "",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "FIaxZkJNOmj3MjPNgo2tFvZOXvWbNAdlAWWaAZnb9fg="
                }
            ]
        },
        {
            "id": 5760586365272064,
            "name": "product_2",
            "description": "product_2",
            "authCallback": "",
            "apiRules": null,
            "apiMeta": "",
            "userRules": [
                {
                    "verb": "GET",
                    "path": "/hello/hi",
                    "effect": true
                }
            ],
            "userMeta": "",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "II4htdb2eUx0FKDrA7Fr0INyd4WsamLlrzCIjKW8fTI="
                }
            ]
        },
        {
            "id": 5750501782061056,
            "name": "product_3",
            "description": "product_3",
            "authCallback": "",
            "apiRules": null,
            "apiMeta": "",
            "userRules": null,
            "userMeta": "",
            "apiKeys": [
                {
                    "name": "default",
                    "value": "aIsKmHDTaSvYJ7JBzc5_QsnJZ4UWJFwMgt5AIA4Oyvs="
                }
            ]
        }
    ]
}
```

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/product`

### Returns

Returns list of products if a valid authorization key was provided, and returns an error otherwise.

## Create Product

> Definition

```
POST  https://[GOODCOP_URL]/v1/product

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product"
  -X POST
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	    "name":"test_product"
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 6308443803615232,
    "name": "test_product",
    "description": "",
    "authCallback": "",
    "apiRules": null,
    "apiMeta": "",
    "userRules": null,
    "userMeta": "",
    "apiKeys": [
        {
            "name": "default",
            "value": "test_2va8vfZ4j1Ci1qvGreQ-u8OwD3LjYQ9ksegxEp0="
        }
    ]
}

```

Creates a product provided the name in the request body.

<aside style="background:#f0ad4e;">
The Authorization token is a super secure token that is only accessible to administrators of Goodcop Api.
</aside>

### HTTPS Request

`POST https://[GOODCOP_URL]/v1/group`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | required | string | The name of the product.
 

### Returns

Returns product object if correct type of name is provided, and returns an error otherwise.

## Get Product By ID

Retrieves the details of a product. Provide the unique product ID and Goodcop will return the corresponding user information.

> Definition

```
GET  https://[GOODCOP_URL]/v1/product/{productID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5735995932672000"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "id": 5735995932672000,
    "name": "product_1",
    "description": "123",
    "authCallback": "https://requestb.in/1f4y9ho1",
    "apiRules": [
        {
            "verb": "POST",
            "path": "/product_1/billing",
            "effect": false
        },
        {
            "verb": "POST",
            "path": "/product_1/billin",
            "effect": true
        },
        {
            "verb": "POST",
            "path": "/dkd",
            "effect": false
        }
    ],
    "apiMeta": "123",
    "userRules": null,
    "userMeta": "",
    "apiKeys": [
        {
            "name": "default",
            "value": "test_3MjPNgo2tFvZOXvWbNAdlAWWaAZnb9fg="
        }
    ]
}

```

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/product/{productID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns product detauls if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Product By ID

Provide the product details and Goodcop will return the updated product information.

> Definition

```
PUT  https://[GOODCOP_URL]/v1/product/{productID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/6308443803615232"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	"name":"test_product",
	"description":"This is test description",
	"apiMeta": "test meta",
	"authCallback":"/callback",
	"apiRules":[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
		
	}],
	"userRules":[{
            "verb": "GET",
            "path": "/new/5687539843203072",
            "effect": true
		
	}],
	"userMeta":"user meta"
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
	"name":"test_product",
	"description":"This is test description",
	"apiMeta": "test meta",
	"authCallback":"/callback",
	"apiRules":[{
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
		
	}],
	"userRules":[{
            "verb": "GET",
            "path": "/new/5687539843203072",
            "effect": true
		
	}],
	"userMeta":"user meta"
}

```

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/product/{productID}`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
name | optional | string | name of the product
description | optional | string |  description of the product 
authCallback | optional | string | define a callback for federated auth 
apiMeta | optional | string | meta information of the api 
apiRules | optional | array | rules of api
userMeta | optional | string | meta information of the user 
userRules | optional | array | rules of user  

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid user identifier 

### Returns

Returns product object if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Product By ID

Provide the unique product ID and Goodcop will return the message for successful deletion of product.

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/product/{productID}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5178306911535104"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Product Deleted Successfully"
}
```

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/product/{productID}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns a string message if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Update Product Meta By ID

Provide the unique product ID and Goodcop will return the meta details.

> Definition

```
PUT  https://[GOODCOP_URL]/v1/product/{productID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5178306911535104/meta"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: user" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d '{
	    "meta":"meta updated successfully"
    }'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "meta updated successfully"
}
```
<aside style="background:#5bc0de;">
The category header can be provided with two options either api or user depending on which type meta you want to change 
</aside>

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/product/{productID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns message string if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Get Product Meta By ID

Provide the unique product ID and Goodcop will return the meta details.

> Definition

```
GET  https://[GOODCOP_URL]/v1/product/{productID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5178306911535104/meta"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: api" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "apiMeta": "test meta"
}
```

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/product/{productID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns meta string if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Product Meta By ID

Provide the unique product ID and Goodcop will delete the meta string.

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/product/{productID}/meta

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5178306911535104/meta"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: api" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "meta deleted successfully"
}
```

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/product/{productID}/meta`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns success message string if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Get Product Rules By ID

Provide the unique product ID and Goodcop will return the rule details.

> Definition

```
GET  https://[GOODCOP_URL]/v1/product/{productID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5178306911535104/rule"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: api" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "apiRules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
}
```

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/product/{productID}/rule`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns rules array if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Update Product Rules By ID

Provide the unique product ID, rule array and Goodcop will return the updated rule details.

> Definition

```
PUT  https://[GOODCOP_URL]/v1/product/{productID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5178306911535104/rule"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: api" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d ' [
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "apiRules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        },
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
}
```

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/product/{productID}/rule`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be updated 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns updated rules array if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Product Rules By ID

Provide the unique product ID, rule array and Goodcop will return the updated rule details.

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/product/{productID}/rule

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/5178306911535104/rule"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "category: api" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
  -d ' [
        {
            "verb": "PUT",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
'
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "apiRules": [
        {
            "verb": "GET",
            "path": "/credentials/5687539843203072",
            "effect": true
        }
    ]
}
```

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/product/{productID}/rule`

### Request Body

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
rules | required | array | rules to be deleted 

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier 

### Returns

Returns updated rules array if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Create Product APIKey By ID

> Definition

```
PUT  https://[GOODCOP_URL]/v1/product/{productID}/apikey/{apikeyname}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/6308443803615232/apikey/testKey"
  -X PUT
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "ApiKeys": [
        {
            "name": "default",
            "value": "1y4y2va8vfZ4j1Ci1qvGreQ-u8OwD3LjYQ9ksegxEp0="
        },
        {
            "name": "testKey",
            "value": "yIaoGc11rS8g0sTh6Iz1QFz-nvnK6Ou3j5VxZ9z_6JU="
        }
    ]
}

```

Creates a new product api key with the name in url params.

### HTTPS Request

`PUT https://[GOODCOP_URL]/v1/product/{productID}/apikey/{apikeyname}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier
apikeyname | required | string | Name of the api key to be generated
 

### Returns

Returns array of ApiKeys if a valid authorization key and a valid identifier was provided, and returns an error otherwise.


## Get Product APIKey By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/product/{productID}/apikey/{apikeyname}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/6308443803615232/apikey/testKey"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "name": "testKey",
    "value": "yIaoGc11rS8g0sTh6Iz1QFz-nvnK6Ou3j5VxZ9z_6JU="
}

```

Provide the unique product ID, ApiKey Name and Goodcop will return the key details.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/product/{productID}/apikey/{apikeyname}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier
apikeyname | required | string | Name of the api key to be generated
 

### Returns

Returns array of ApiKeys if a valid authorization key and a valid identifiers were provided, and returns an error otherwise.


## Get All Product APIKeys By ID

> Definition

```
GET  https://[GOODCOP_URL]/v1/product/{productID}/apikey

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/6308443803615232/apikey"
  -X GET
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "ApiKeys": [
        {
            "name": "default",
            "value": "1y4y2va8vfZ4j1Ci1qvGreQ-u8OwD3LjYQ9ksegxEp0="
        },
        {
            "name": "testKey",
            "value": "yIaoGc11rS8g0sTh6Iz1QFz-nvnK6Ou3j5VxZ9z_6JU="
        }
    ]
}

```

Provide the unique product ID and Goodcop will return the all available keys details.

### HTTPS Request

`GET https://[GOODCOP_URL]/v1/product/{productID}/apikey/`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier

### Returns

Returns array of ApiKeys if a valid authorization key and a valid identifier was provided, and returns an error otherwise.

## Delete Product APIKey By ID

> Definition

```
DELETE  https://[GOODCOP_URL]/v1/product/{productID}/apikey/{apikeyname}

```
> Example Request

```shell
curl "https://[GOODCOP_URL]/v1/product/6308443803615232/apikey/testKey"
  -X DELETE
  -H "Authorization: test_aIsKmHDTaSvYJGHGHJ5_QsnJZ4UWJFwMgt5AIA4Oyvs=" \
  -H "Content-Type: application/json" \
  -H "Device-Identifier: test_56789657567"
```

> Example Response <code style="background:#4CAF50;"> 200</code>

```json
{
    "message": "Key deleted successfuly."
}

```

Provide the unique product ID, ApiKey Name and Goodcop will delete the api key.

### HTTPS Request

`DELETE https://[GOODCOP_URL]/v1/product/{productID}/apikey/{apikeyname}`

### URL Params

Parameter | Value | Type | Description
--------- | ------- | --------------- | -----------
productID | required | string | Valid product identifier
apikeyname | required | string | Name of the api key to be generated
 

### Returns

Returns string message if a valid authorization key and a valid identifiers were provided, and returns an error otherwise.