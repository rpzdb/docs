# Hosts

## List All Hosts
You may list collection of hosts using this action.


```shell
curl --include \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
  'http://manage.rpzdb.com/api/v1/zones/36/hosts'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 344,
        "blacklist_data": "lalalax.com",
        "created_at": "2018-01-22T08:59:51Z",
        "updated_at": "2018-01-22T11:06:12Z",
        "record_type": "A",
        "content": "2.2.2.2",
        "tags": [
            "yolo",
            "hello"
        ]
    },
    {
        "id": 346,
        "blacklist_data": "pp.my",
        "created_at": "2018-01-22T09:25:55Z",
        "updated_at": "2018-01-22T09:25:55Z",
        "record_type": "A",
        "content": "1.3.4.5",
        "tags": []
    }
]
```

This endpoint retrieves all hosts.

### HTTP Request

`GET http://manage.rpzdb.com/api/v1/zones/:zone_id/hosts`

## Create Zone

You may create a host using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
    \"blacklist_data\": \"labs.com.my\",
    \"record_type\": \"1\",
    \"destination\": \"1.1.1.1\",
    \"user_tag_list\": \"danger,underated\"
}" \
'http://manage.rpzdb.com/api/v1/zones/36'
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




## Show Host


```shell
curl --include \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
  'http://manage.rpzdb.com/api/v1/zones/36/hosts/359'
```


> The above command returns JSON structured like this:

```json
{
    "id": 359,
    "blacklist_data": "faraa.demo.my",
    "created_at": "2018-01-22T10:10:11Z",
    "updated_at": "2018-01-22T10:38:07Z",
    "record_type": "A",
    "content": "1.1.1.100",
    "tags": [
        "yolo",
        "hello",
        "ajajja"
    ]
}
```

This endpoint retrieves a host.

### HTTP Request

`GET http://manage.rpzdb.com/api/v1/zones/:zone_id/hosts/:id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the host to retrieve

## Delete Host
```shell
curl --include \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
     --request DELETE \
  'http://manage.rpzdb.com/api/v1/zones/36/hosts/2'
```


> The above command returns JSON structured like this:

```json
{
    "id": 359,
    "blacklist_data": "faraa.demo.my",
    "created_at": "2018-01-22T10:10:11Z",
    "updated_at": "2018-01-22T10:38:07Z",
    "record_type": null,
    "content": null,
    "tags": [],
    "message": "Host Deleted!"
}
```

This endpoint delete a host.


### HTTP Request

`DELETE http://manage.rpzdb.com/api/v1/zones/:zone_id/hosts/:id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the host to delete

