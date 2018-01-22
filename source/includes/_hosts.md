# Hosts

## Get All Hosts


```shell
curl --include \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
  'http://manage.rpzdb.com/api/v1/hosts'
```

> The above command returns JSON structured like this:

```json
[
    {
        {
            "id": 5,
            "node_name": "elastic2.dnsvault.net",
            "description": null,
            "created_at": "2016-06-22T16:10:10.602Z",
            "updated_at": "2016-06-22T16:10:10.602Z",
            "tag": "agent",
            "fingerprint": "64:9E:06:F0:0C:AB:0F:63:2B:0D:DC:C6:E2:DF:BE:33:8F:69:3C:A0:99:D8:1F:65:76:AE:EA:DA:C6:64:12:3F",
            "fingerprint_algorithm": "SHA256"
        }
    }
]
```

This endpoint retrieves all hosts.

### HTTP Request

`GET http://manage.rpzdb.com/api/v1/hosts`



## Get a Host


```shell
curl --include \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
  'http://manage.rpzdb.com/api/v1/hosts/2'
```


> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "node_name": "elastic2.dnsvault.net",
  "description": null,
  "created_at": "2016-06-22T16:10:10.602Z",
  "updated_at": "2016-06-22T16:10:10.602Z",
  "tag": "agent",
  "fingerprint": "64:9E:06:F0:0C:AB:0F:63:2B:0D:DC:C6:E2:DF:BE:33:8F:69:3C:A0:99:D8:1F:65:76:AE:EA:DA:C6:64:12:3F",
  "fingerprint_algorithm": "SHA256"
}
```

This endpoint retrieves a node.

### HTTP Request

`GET http://manage.rpzdb.com/api/v1/hosts/:id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the node to retrieve

## Delete a Host
```shell
curl --include \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
     --request DELETE \
  'http://manage.rpzdb.com/api/v1/hosts/2'
```


> The above command returns JSON structured like this:

```json
{
  "success": {
    "7005": "Host has been deleted"
  }
}
```

This endpoint delete a node.


### HTTP Request

`DELETE http://manage.rpzdb.com/api/v1/hosts/:id`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the node to delete

