---
title: API Reference

language_tabs:
  - html/javascript
  - Wordpress
  - Drupal

toc_footers:
  - <a href='http://www.naytev.com'>Go back to NAYTEV</a>

includes:
  - errors

---

# Introduction

Welcome to the NAYTEV documentation. In just a few minutes (usually under 5), we'll have you running experiments on your website.

All you have to do to integrate NAYTEV with your existing share buttons is add one line of code to your website to include the NAYTEV javascript library.

If you don't already have share buttons, we'll add those too (they are also just a single line of code). NAYTEV is compatible out of the box with about 95% of existing share buttons across the web, so chances are we'll work with your existing ones if you have them.

# Installation

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

# Create a Facebook App

1. Login to Facebook with the account you normally use. 
1. Visit <a href="http://developers.facebook.com" target="_blank">Facebook's Developers Page</a> (if prompted, accept the Terms of Service) 
1. On the top left, click the “Apps” dropdown,  and select “Create New App” ![create app](facebook/createApp.png)
1. Give your App a name (your users will see this name when they Share) and choose the category “Apps for Pages” 
1. On your new App Dashboard, copy the App ID as you will need it in the next section. ![create app](facebook/appID.png)
1. On the left, navigate to the “Settings” tab. Enter your website’s address in “App Domain”, your email address in “Contact email”, and then click “Add a Platform” ![create app](facebook/addPlatform.png)
1. Select “Website” ![create app](facebook/website.png)
1. Enter your website’s information, then click Save. Note: It’s important that the site you enter here matches the site where your users will be sharing. For security purposes, shares the don’t match will be ignored. ![create app](facebook/websiteDetails.png)
1. Activate your app.  On the “Status & Review” tab, change toggle button indicated by the red arrow on the right from “No” to “Yes”. ![create app](facebook/activate.png)
1. You’re good to go! Head over to NAYTEV and you can start using your shiny new app immediately. 

<aside class="notice">
The domain (website) of your Facebook App must match the site you're installing NAYTEV on. This is a security measure, and experiments will be ignored when the domain doesn't match.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
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
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the cat to retrieve

