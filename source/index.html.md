---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - php
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='https://developers.hollatags.com'>Sign Up for a Developer Key</a>

includes:
  - sms
  - voice
  - ussd
  - lookup
  - errors

search: true
---

# Introduction

Welcome to the HollaTags API! You can use any of the Voice, SMS, USSD and Lookup API endpoints for your integration.

We have language bindings in PHP, Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

HollaTags uses API keys to allow access to the Voice, SMS, USSD and Lookup API. You can register a new API key at our [developer portal](http://developers.hollatags.com).

HollaTags expects the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your developer API key.
</aside>

