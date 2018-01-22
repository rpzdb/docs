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
        "id": 52,
        "zone_name": "satu.com",
        "view_id": 50,
        "description": "",
        "zone_type": "master",
        "status": "active",
        "processing_status": true,
        "backend_status": false,
        "delete_status": false,
        "position": 1,
        "serial_number": null,
        "created_at": "2017-03-31T09:21:19.406Z",
        "updated_at": "2017-06-16T03:18:11.521Z"
    },
    {
        "id": 80,
        "zone_name": "yola.com",
        "view_id": 50,
        "description": "",
        "zone_type": "master",
        "status": "active",
        "processing_status": true,
        "backend_status": false,
        "delete_status": false,
        "position": 2,
        "serial_number": null,
        "created_at": "2017-07-03T03:03:25.766Z",
        "updated_at": "2017-07-03T03:03:25.857Z"
    },
    {
        "id": 81,
        "zone_name": "yoooow.com",
        "view_id": 50,
        "description": "",
        "zone_type": "master",
        "status": "active",
        "processing_status": true,
        "backend_status": false,
        "delete_status": false,
        "position": 3,
        "serial_number": null,
        "created_at": "2017-07-03T03:04:49.595Z",
        "updated_at": "2017-07-03T03:04:49.688Z"
    }
]
```

This endpoint get list of zones.

### HTTP Request

`GET http://manage.rpzdb.com/api/v1/zones`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the node to retrieve

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
    "id": 91,
    "view_id": 50,
    "zone_name": "labs.com.my",
    "description": "this is new domain",
    "zone_type": "master",
    "position": 5,
    "serial_number": null,
    "status": "active",
    "read_only": false,
    "processing_status": false,
    "backend_status": false,
    "delete_status": false,
    "write": false,
    "deleted_at": null,
    "created_at": "2017-07-11T10:22:22.567Z",
    "updated_at": "2017-07-11T10:22:22.567Z"
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
  'http://manage.rpzdb.com/api/v1/zones/91'
```

> The above command returns JSON structured like this:

```json
{
    "id": 91,
    "zone_name": "labs.com.my",
    "view_id": 50,
    "description": "this is new domain",
    "zone_type": "master",
    "status": "active",
    "processing_status": true,
    "backend_status": false,
    "delete_status": false,
    "position": 5,
    "serial_number": null,
    "created_at": "2017-07-11T10:22:22.567Z",
    "updated_at": "2017-07-11T10:22:22.598Z",
    "view": {
        "id": 50,
        "node_id": 2,
        "view_name": "cloudlocal",
        "description": "",
        "status": "active",
        "position": 0,
        "created_at": "2017-03-31T09:17:41.743Z",
        "updated_at": "2017-03-31T09:17:41.766Z"
    },
    "node": {
        "id": 2,
        "node_name": "dnsvnode1",
        "description": "this is node1",
        "tag": "agent",
        "fingerprint": "EF:41:67:B5:52:F7:1F:D2:67:B3:48:99:89:0C\n:6E:FE:F2:D7:5C:E5:34:38:14:26:1F:D3:D9:AD:02:2E:53:1C",
        "fingerprint_algorithm": "SHA256"
    }
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
[
{
  "success": {
    "7005": "Zone has been deleted"
  }
}
]
```

This endpoint delete a zone.

### HTTP Request

`DELETE http://manage.rpzdb.com/api/v1/zones/:id`