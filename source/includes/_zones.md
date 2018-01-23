# RPZ Zones

## List all RPZ Zones
You may list collection of rpz zones using this action.

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
        "updated_at": "2013-04-05T19:29:22Z",
        "statements": [
            {
                "id": 12,
                "statement": "also-notify",
                "address": "8.8.8.8",
                "port": 53
            },
            {
                "id": 13,
                "statement": "also-notify",
                "address": "4.4.4.4",
                "port": 53
            }
        ]
    },
    {
        "id": 82,
        "zone_name": "blackhole",
        "combine": "blackhole.ap-southeast.rpzdb.com",
        "server_name": "ap-southeast.rpzdb.com",
        "server_ip": "175.41.131.248",
        "created_at": "2018-01-23T04:06:02Z",
        "updated_at": "2018-01-23T04:06:02Z",
        "tsig": {
            "id": 32,
            "keyname": "blackhole",
            "algorithm": "HMAC-SHA1",
            "algorithm_size": "128",
            "secret": "mtIsHR3rqQKx1EfkQNIQIA=="
        },
        "statements": [
            {
                "id": 43,
                "statement": "also-notify",
                "address": "192.168.3.1",
                "port": 53
            }
        ]
    }
]
```

This endpoint get list of  rpz zones.

### HTTP Request

`GET http://manage.rpzdb.com/api/v1/zones`

### OPTIONAL ARGUMENTS

Parameter | Description
--------- | -----------
page | Up to 20 results will be returned in a single API call per specified page. Default to 1 if not present.


## Create RPZ Zone

You may create a rpz zone using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
  \"zone_name\": \"blackhole\",
  \"site_ip\": \"192.168.3.1\",
  \"feed_server\": \"ap-southeast.rpzdb.com\"
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

This endpoint create a rpz zone.

### HTTP Request

`POST http://manage.rpzdb.com/api/v1/zones`

### REQUIRED ARGUMENTS

Parameter | Description
--------- | -----------
zone_name | Rpz zone name
site_ip | DNS server ip destination


### OPTIONAL ARGUMENTS

Parameter | Description
--------- | -----------
feed_server | Blacklist provider server address


### RESPONSE PARAMETER

Parameter | Description
--------- | -----------
id | The ID of the selected zone
zone_name | Selected zone name
combine | Combined of zone name
server_name | Server name
server_ip | Server ip address
created_at | Date and time created
updated_at |  Date and time updated
tsig[id] | Transaction signature id
tsig[keyname] | Transaction signature keyname
tsig[algorithm] | Transaction signature algorithm
tsig[algorithm_size] | Transaction signature size
tsig[secret] | Transaction signature secret
statement[] | Contains notify statement



## Show RPZ Zone

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

`GET http://manage.rpzdb.com/api/v1/zones/:id`

### URL PARAMETER

Parameter | Description
--------- | -----------
id | The ID of the zone to show

### RESPONSE PARAMETER
Parameter | Description
--------- | -----------
id | The ID of the selected zone
zone_name | Selected zone name
combine | Combined of zone name
server_name | Server name
server_ip | Server ip address
created_at | Date and time created
updated_at |  Date and time updated
tsig[id] | Transaction signature id
tsig[keyname] | Transaction signature keyname
tsig[algorithm] | Transaction signature algorithm
tsig[algorithm_size] | Transaction signature size
tsig[secret] | Transaction signature secret
statement[] | Contains notify statement


## Delete RPZ Zone

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

### URL PARAMETER

Parameter | Description
--------- | -----------
id | The ID of the zone to delete

### RESPONSE PARAMETER

Parameter | Description
--------- | -----------
id | The ID of the deleted zone
zone_name | Deleted zone name
status | Deleted status
