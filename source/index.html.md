---
title: API Reference

language_tabs:
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://www.ab-it.io'>Ypsilon is powered by AB-IT</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Ypsilon API! You can use our API to access Ypsilon API endpoints.

Language binding in node.js & javascript is coming up, stay tuned!

Every Ypsilon plugin API has its own docs which you can find at http://man.[PLUGINNAME].ypsilon.club.



# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api.ypsilon.club/auth"
  -H "Authorization: your_dev_key"
```

```javascript
const ypsilon = require('ypsilon');

let api = ypsilon.authorize('your_dev_key');
```

> Make sure to replace `your_dev_key` with your API key.

Ypsilon uses API keys to allow access to the API. You can register a new Ypsilon API key at our [developer portal](http://ypsilon.club).

Ypsilon expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: your_dev_key`

<aside class="notice">
You must replace <code>your_dev_key</code> with your personal API key.
</aside>

# Products

## Get All Products

```shell
curl "http://api.ypsilon.club/products"
  -H "Authorization: your_dev_key"
```

```javascript
const ypsilon = require('ypsilon');

let api = kittn.authorize('your_dev_key');
let products = api.posts.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all products from your woocommerce store.

### HTTP Request

`GET http://api.ypsilon.club/products`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_trashed | false | If set to true, the result will also include trashed products.

<aside class="success">
Remember — Authenticate!
</aside>

## Get a Specific Product

```shell
curl "http://api.ypsilon.club/products/2"
  -H "Authorization: your_dev_key"
```

```javascript
const ypsilon = require('ypsilon');

let api = ypsilon.authorize('your_dev_key');
let product = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific prodcuts.

<aside class="warning">If there is no product found the api will return <code>{}</code></aside>

### HTTP Request

`GET http://api.ypsilon.club/products/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the product to retrieve

