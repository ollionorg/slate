---
title: Data Agrregator API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - Endpoint

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Data aggregator API! You can use this API to access Data aggregator API endpoints, which can get information on various channels, users, and chats from redis.

Click to check the api status: [Status Check](http://localhost:3000).


# Channels

## Get All Channels


```Endpoint
<host>/channels
```

> The above API returns JSON structured like this:

```json
{
  "channels": [
    {
      "blacklists": {
        "user_id": []
      },
      "channel_id": 104,
      "chats": {
        "total_brodcast": 870,
        "total_received": 59702
      },
      "users": {
        "total_concurrent": -26,
        "total_concurrent_guests": 5,
        "total_concurrent_users": -31,
        "total_guests": 5,
        "total_users": 3
      }
    },
    {
      "blacklists": {
        "user_id": []
      },
      "channel_id": 96,
      "chats": {
        "total_brodcast": 2764,
        "total_received": 266859
      },
      "users": {
        "total_concurrent": 722,
        "total_concurrent_guests": 27,
        "total_concurrent_users": 695,
        "total_guests": 27,
        "total_users": 4
      }
    }
  ]
}
```

This endpoint retrieves data for all channels availble in redis.

### HTTP Request

`GET http://example.com/channels`

### URL Parameters

Parameter | Description
--------- | -----------
channel_id | The ID of the channel to retrieve

<aside class="success">
Returns — Status 200
</aside>


## Get a Specific Channel

```Endpoint
<host>/channels?channel_id=96
```

> The above command returns JSON structured like this:

```json
{
   "channels":[
      {
         "active":true,
         "blacklists":{
            "user_id":[]
         },
         "channel_id":96,
         "chats":{
            "total_brodcast":2764,
            "total_received":266859
         },
         "users":{
            "total_concurrent":722,
            "total_concurrent_guests":27,
            "total_concurrent_users":695,
            "total_guests":27,
            "total_users":4
         }
      }
   ]
}
```


### HTTP Request

`GET http://example.com/channels/?channel_id=96`


### URL Parameters

Parameter | Description
--------- | -----------
channel_id | The ID of the channel to retrieve

<aside class="success">
Returns — Status 200
</aside>

## Get all active Channels

> The above command returns JSON structured like this:

```json
{
   "channels":[
      {
         "active":true,
         "blacklists":{
            "user_id":[
               8965646
            ]
         },
         "channel_id":104,
         "chats":{
            "total_brodcast":870,
            "total_received":59702
         },
         "users":{
            "total_concurrent":-26,
            "total_concurrent_guests":5,
            "total_concurrent_users":-31,
            "total_guests":5,
            "total_users":3
         }
      },
      {
         "active":true,
         "blacklists":{
            "user_id":[

            ]
         },
         "channel_id":96,
         "chats":{
            "total_brodcast":2764,
            "total_received":266859
         },
         "users":{
            "total_concurrent":722,
            "total_concurrent_guests":27,
            "total_concurrent_users":695,
            "total_guests":27,
            "total_users":4
         }
      }
   ]
}
```

### HTTP Request

`GET http://example.com/channels/?active=true`

### URL Parameters

Parameter | Description
--------- | -----------
active     | The status of the channel to retrieve

<aside class="success">
Returns — Status 200
</aside>

## Get an active Channel


> The above command returns JSON structured like this:

```json
{
   "channels":[
      {
         "active":true,
         "blacklists":{
            "user_id":[
               8965646
            ]
         },
         "channel_id":104,
         "chats":{
            "total_brodcast":870,
            "total_received":59702
         },
         "users":{
            "total_concurrent":-26,
            "total_concurrent_guests":5,
            "total_concurrent_users":-31,
            "total_guests":5,
            "total_users":3
         }
      },
      {
         "active":true,
         "blacklists":{
            "user_id":[

            ]
         },
         "channel_id":96,
         "chats":{
            "total_brodcast":2764,
            "total_received":266859
         },
         "users":{
            "total_concurrent":722,
            "total_concurrent_guests":27,
            "total_concurrent_users":695,
            "total_guests":27,
            "total_users":4
         }
      }
   ]
}
```


### HTTP Request

`GET http://example.com/kittens/?channel_id=96&active=true`

### URL Parameters

Parameter | Description
--------- | -----------
channel_id | The ID of the channel to retrieve
active     | The status of the channel to retrieve


<aside class="success">
Returns — Status 200
</aside>



# Chats

## Get All Chats

> The above API returns JSON structured like this:

```json
{
  "channel_id": "96",
  "users": [
    {
      "chat_in-channel": 2,
      "total_chats": 2,
      "user_id": "5513252"
    },
    {
      "chat_in-channel": 78176,
      "total_chats": 96408,
      "user_id": "8965643"
    },
    {
      "chat_in-channel": 57980,
      "total_chats": 57980,
      "user_id": "8965644"
    },
    {
      "chat_in-channel": 130701,
      "total_chats": 130701,
      "user_id": "8965645"
    }
  ]
}
```

This endpoint retrieves data for all channels availble in redis.

### HTTP Request

`GET http://example.com/chats`

<aside class="success">
Returns — Status 200
</aside>

<aside class="notice">
This API does not have timestamps in parameters. So response does not have chat_in_period key.
</aside>

## Get Chat for a specific Channel

> The above API returns JSON structured like this:

```json
{
  "channel_id": 96,
  "users": [
    {
      "chat_in-channel": 2,
      "total_chats": 2,
      "user_id": 5513252
    },
    {
      "chat_in-channel": 78176,
      "total_chats": 96408,
      "user_id": 8965643
    },
    {
      "chat_in-channel": 57980,
      "total_chats": 57980,
      "user_id": 8965644
    },
    {
      "chat_in-channel": 130701,
      "total_chats": 130701,
      "user_id": 8965645
    }
  ]
}
```

### HTTP Request

`GET http://example.com/chats?channel_id=96`

<aside class="success">
Returns — Status 200
</aside>

<aside class="notice">
This API does not have timestamps in parameters. So response does not have chat_in_period key.
</aside>

## Get Chat for a specific Channel with start timestamp

> The above API returns JSON structured like this:

```json
{
  "channel_id": 96,
  "ts_start": 1539939879,
  "users": [
    {
      "chat_in-channel": 2,
      "chats_in_period": 0,
      "total_chats": 2,
      "user_id": 5513252
    },
    {
      "chat_in-channel": 78176,
      "total_chats": 96408,
      "user_id": 8965643
    },
    {
      "chat_in-channel": 57980,
      "total_chats": 57980,
      "user_id": 8965644
    },
    {
      "chat_in-channel": 130701,
      "total_chats": 130701,
      "user_id": 8965645
    }
  ]
}
```

### HTTP Request

`GET http://example.com/chats?channel_id=96&ts_start=1539939879`

<aside class="success">
Returns — Status 200
</aside>

<aside class="notice">
chats_in_period key will be returned for the users(those were active at the given timestamp)
</aside>

## Get Chat for a specific Channel with start and end timestamp

> The above API returns JSON structured like this:

```json
{
  "channel_id": 96,
  "ts_start": 1539939879,
  "users": [
    {
      "chat_in-channel": 2,
      "chats_in_period": 0,
      "total_chats": 2,
      "user_id": 5513252
    },
    {
      "chat_in-channel": 78176,
      "total_chats": 96408,
      "user_id": 8965643
    },
    {
      "chat_in-channel": 57980,
      "total_chats": 57980,
      "user_id": 8965644
    },
    {
      "chat_in-channel": 130701,
      "total_chats": 130701,
      "user_id": 8965645
    }
  ]
}
```


### HTTP Request

`GET http://example.com/chats?channel_id=96&ts_start=1539939879&ts_end=1539944558`

<aside class="success">
Returns — Status 200
</aside>

<aside class="notice">
chats_in_period key will be returned for the users(those were active at the given timestamp)
</aside>


# Chat_Aggregate

## Get All Chat Aggregate

> The above API returns JSON structured like this:

```json
{
  "chat_agg": {
    "users": [
      {
        "total_chats": 96408,
        "user_id": 8965643
      },
      {
        "total_chats": 4462,
        "user_id": 8965646
      },
      {
        "total_chats": 37008,
        "user_id": 8965648
      },
      {
        "total_chats": 2,
        "user_id": 5513252
      },
      {
        "total_chats": 96408,
        "user_id": 8965643
      },{},{}
    ]
  }
}
```

This endpoint retrieves chat data for all channels availble in redis.

### HTTP Request

`GET http://example.com/chat_aggregate/`

<aside class="success">
Returns — Status 200
</aside>

## Get All Chat Aggregate from a timestamp

> The above API returns JSON structured like this:

```json
{
  "chat_agg": {
    "ts_start": 1539939879,
    "users": [
      {
        "chats_in_period": 0,
        "total_chats": 2,
        "user_id": 5513252
      },
      {
        "chats_in_period": 4,
        "total_chats": 96408,
        "user_id": 8965643
      },
      {
        "chats_in_period": 0,
        "total_chats": 57980,
        "user_id": 8965644
      },
      {
        "chats_in_period": 3,
        "total_chats": 130701,
        "user_id": 8965645
      },{},{}
    ]
  }
}
```

This endpoint retrieves chat data for all channels from given start timestamp untill last.

### HTTP Request

`GET http://example.com/chat_aggregate?ts_start=1539939879`

<aside class="success">
Returns — Status 200
</aside>


## Get All Chat Aggregate from a timestamp until end timestamp

> The above API returns JSON structured like this:

```json
{
  "chat_agg": {
    "ts_start": 1539939879,
    "users": [
      {
        "chats_in_period": 0,
        "total_chats": 2,
        "user_id": 5513252
      },
      {
        "chats_in_period": 4,
        "total_chats": 96408,
        "user_id": 8965643
      },
      {
        "chats_in_period": 0,
        "total_chats": 57980,
        "user_id": 8965644
      },
      {
        "chats_in_period": 3,
        "total_chats": 130701,
        "user_id": 8965645
      },{},{}
    ]
  }
}
```

This endpoint retrieves chat data for all channels from given start timestamp untill last timestamp.

### HTTP Request

`GET http://example.com/chat_aggregate?ts_start=1539939879&ts_end=1539945364`

<aside class="success">
Returns — Status 200
</aside>