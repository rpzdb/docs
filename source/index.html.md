---
title: RPZdb - API Reference

language_tabs:
    - shell

toc_footers:
  - <a href='www.rpzdb.com/sign_in'>Sign Up for a Developer Key</a>
  - <a href='https://www.rpzdb.com'>Visit Site</a>

includes:
  - zones
  - hosts
  - search

search: true
---

# Introduction

Welcome to the RPZdb API! You can use our API to access RPZdb API endpoints, which can get information on nodes, views, zones, records and others that is related to our RPZdb Appliance. 

We have language bindings in Shell! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "rpzdb.com"
  -H "Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe"
```


> Make sure to replace `iwwTXK54aahsosrx5JK7hkTe` with your API key.

RPZdb uses API keys to allow access to the API. You can register a new RPZdb API key at our [developer portal](http://manage.rpzdb.com/developers).

RPZdb expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Token token=iwwTXK54aahsosrx5JK7hkTe`

<aside class="notice">
You must replace <code>iwwTXK54aahsosrx5JK7hkTe</code> with your personal API key.
</aside>



