# Blacklist

## List All Blacklist
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

`GET http://manage.rpzdb.com/api/v1/zones/:zone_name/hosts`

### URL PARAMETER

Parameter | Description
--------- | -----------
zone_name | Rpz zone name


### OPTIONAL ARGUMENTS

Parameter | Description
--------- | -----------
page | Up to 20 results will be returned in a single API call per specified page. Default to 1 if not present.


## Create Blacklist

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
'http://manage.rpzdb.com/api/v1/zones/36/hosts'
```

> The above command returns JSON structured like this:

```json
{
    "id": 361,
    "blacklist_data": "malam.demo.my",
    "created_at": "2018-01-22T15:14:56Z",
    "updated_at": "2018-01-22T15:14:56Z",
    "record_type": "A",
    "content": "1.1.1.1",
    "tags": [
        "yolo",
        "hello"
    ]
}
```

This endpoint create a zone.

### HTTP Request

`POST http://manage.rpzdb.com/api/v1/zones/:zone_name/hosts`

### URL PARAMETER

Parameter | Description
--------- | -----------
zone_name | Rpz zone name

### REQUIRED ARGUMENTS

Parameter | Description
--------- | -----------
blacklist_data | Blacklist data
destination | Destination
user_tag_list | Tagging associate with the host

### OPTIONAL ARGUMENTS

Parameter | Description
--------- | -----------
record_type | Record Type

### Record Type

Value | Description
--------- | -----------
1 | A or AAAA
2 | CNAME
3 | NXDOMAIN
4 | NODATA


### RESPONSE PARAMETER
Parameter | Description
--------- | -----------
id | The ID of the selected host
blacklist_data | Blacklist data
record_type | Record Type
content | Record data
tags | Tagging associate with the host
created_at | Date and time created
updated_at |  Date and time updated


## Show Blacklist

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

`GET http://manage.rpzdb.com/api/v1/zones/:zone_name/hosts/:id`

### URL PARAMETER

Parameter | Description
--------- | -----------
zone_name | Zone Name
id | The ID or Host name to retrieve

### RESPONSE PARAMETER
Parameter | Description
--------- | -----------
id | The ID of the selected host
blacklist_data | Blacklist data
record_type | Record Type
content | Record data
tags | Tagging associate with the host
created_at | Date and time created
updated_at |  Date and time updated


## Delete Blacklist
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

`DELETE http://manage.rpzdb.com/api/v1/zones/:zone_name/hosts/:id`

### URL PARAMETER

Parameter | Description
--------- | -----------
zone_name | Zone Name
id | The ID or Host name to delete

### RESPONSE PARAMETER
Parameter | Description
--------- | -----------
id | The ID of the selected host
blacklist_data | Blacklist data
record_type | Record Type
content | Record data
tags | Tagging associate with the host
created_at | Date and time created
updated_at |  Date and time updated
message | Message from server

