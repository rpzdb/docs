# Zones

## List all Zones
You may list collection of zones using this action.

```shell
curl --include \
     --header "Content-Type: application/json" \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
  'http://manage.rpzdb.com/api/v1/zones'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 3,
        "zone_name": "labs",
        "combine": "labs.us-east.rpzdb.com",
        "server_name": "us-east.rpzdb.com",
        "server_ip": "54.225.70.69",
        "created_at": "2013-04-05T19:29:22Z",
        "updated_at": "2013-04-05T19:29:22Z"
    },
    {
        "id": 62,
        "zone_name": "blackhole",
        "combine": "blackhole.ap-southeast.rpzdb.com",
        "server_name": "ap-southeast.rpzdb.com",
        "server_ip": "175.41.131.248",
        "created_at": "2018-01-22T13:02:19Z",
        "updated_at": "2018-01-22T13:02:19Z"
    }
]
```

This endpoint get list of zones.

### HTTP Request

`GET http://manage.rpzdb.com/api/v1/zones`

### URL Parameters

Parameter | Description
--------- | -----------
id | The ID of the node to retrieve


## Create Zone

You may create a zone using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
    \"zone_name\": \"labs.com.my\",
    \"description\": \"this is new domain\"
}" \
'http://manage.rpzdb.com/api/v1/zones'
```

> The above command returns JSON structured like this:

```json
{
    "id": 62,
    "zone_name": "blackhole",
    "combine": "blackhole.ap-southeast.rpzdb.com",
    "server_name": "ap-southeast.rpzdb.com",
    "server_ip": "175.41.131.248",
    "created_at": "2018-01-22T13:02:19Z",
    "updated_at": "2018-01-22T13:02:19Z",
    "tsig": {
        "id": 23,
        "keyname": "blackhole",
        "algorithm": "HMAC-SHA1",
        "algorithm_size": "128",
        "secret": "KW7qFUTKrKWr+J4qJTKkEw=="
    },
    "statements": [
        {
            "id": 33,
            "statement": "also-notify",
            "address": "192.168.3.1",
            "port": 53
        }
    ]
}
```

This endpoint create a zone.

### HTTP Request

`POST http://manage.rpzdb.com/api/v1/zones`

## Show Zone

You may list a zone using this action.

```shell
curl --include \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
  'http://manage.rpzdb.com/api/v1/zones/62'
```

> The above command returns JSON structured like this:

```json
{
    "id": 62,
    "zone_name": "blackhole",
    "combine": "blackhole.ap-southeast.rpzdb.com",
    "server_name": "ap-southeast.rpzdb.com",
    "server_ip": "175.41.131.248",
    "created_at": "2018-01-22T13:02:19Z",
    "updated_at": "2018-01-22T13:02:19Z",
    "tsig": {
        "id": 23,
        "keyname": "blackhole",
        "algorithm": "HMAC-SHA1",
        "algorithm_size": "128",
        "secret": "KW7qFUTKrKWr+J4qJTKkEw=="
    },
    "statements": [
        {
            "id": 33,
            "statement": "also-notify",
            "address": "192.168.3.1",
            "port": 53
        }
    ]
}
```

This endpoint get list of zones.


### HTTP Request

`PUT http://manage.rpzdb.com/api/v1/zones/:id`

## Delete Zone

You may delete a zone using this action.

```shell
curl --include \
     --request DELETE \
     --header "Content-Type: application/json" \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
  'http://manage.rpzdb.com/api/v1/zones/91'
```

 The above command returns JSON structured like this:

```json
{
    "id": 61,
    "zone_name": "blackhole",
    "status": "deleted"
}
```

This endpoint delete a zone.

### HTTP Request

`DELETE http://manage.rpzdb.com/api/v1/zones/:id`