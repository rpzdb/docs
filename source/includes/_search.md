#Search

## Search Rpz Zone or Blacklist

You may search rpz zone or blacklist using this action. It takes a JSON object containing a parameters.

```shell
curl --include \
     --request POST \
     --header "Content-Type: application/json" \
     --header "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe" \
     --data-binary "{
    \"keyword\": \"amir\",
    \"type\": \"zone\"
}" \
'http://manage.rpzdb.com/api/v1/search'
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 66,
        "zone_name": "amirtest1",
        "combine": "amirtest1.ap-southeast.rpzdb.com",
        "server_name": "ap-southeast.rpzdb.com",
        "server_ip": "175.41.131.248",
        "created_at": "2018-01-22T23:07:03Z",
        "updated_at": "2018-01-22T23:07:03Z"
    },
    {
        "id": 73,
        "zone_name": "amirtest2",
        "combine": "amirtest2.ap-southeast.rpzdb.com",
        "server_name": "ap-southeast.rpzdb.com",
        "server_ip": "175.41.131.248",
        "created_at": "2018-01-22T23:17:35Z",
        "updated_at": "2018-01-22T23:17:35Z"
    }
]
```

This endpoint create a zone.

### HTTP Request

`POST http://manage.rpzdb.com/api/v1/zones/:zone_name/hosts`

### REQUIRED ARGUMENTS

Parameter | Description
--------- | -----------
keyword | Keyword used for search
type | zone or host



