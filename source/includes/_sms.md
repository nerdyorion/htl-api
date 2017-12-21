# SMS

HollaTags provides an API to send and receive SMS messages to and from any country across the world.

Messages are identified by a unique random ID. And with this ID you can always check the status of the message through the provided endpoint.

#### URI

`https://api.hollatags.com/v1/sms/messages`

#### Available HTTP Methods

`POST /messages`

`GET /messages`

`GET /messages/messageId`

`POST /messages/messageId`


## Send SMS

```php
<?php

$url = "https://api.hollatags.com/v1/sms/send";

$from = "MyApp";
$to = array("443xxxxxxx");
$message = "Hello from the other side!";

$params = json_encode(array("from" => $from, "to" => $to, "message" => $message));

$ch = curl_init();  

curl_setopt($ch,CURLOPT_URL, $url);
curl_setopt($ch,CURLOPT_POST, 1);
curl_setopt($ch,CURLOPT_POSTFIELDS, $postvars);
curl_setopt($ch,CURLOPT_RETURNTRANSFER, true);

$output = curl_exec($ch);

curl_close($ch);
return $output;
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

Creates a new message object. HollaTags returns the created message object with each request. Per request, a max of 50 recipients can be entered.

### URI

`POST https://api.hollatags.com/v1/sms/messages`

### Required Parameters

Parameter | Type | Description
--------- | ------- | -----------
from | string | SMS SenderID (must be <= 11 chars for Alphanumerical and <= 16chars for Numerical)
to | array | Destination number(s) (must be in international format and no prefix e.g. 441xxxxxxxx)
message | string | SMS Content (must be <= 905chars)


### Optional Parameters

Parameter | Type | Description
--------- | ------- | -----------
type  | integer | Message Format: `0 = Normal SMS`, `1 = Flash SMS`, `2 = Unicode SMS` (Arabic, Chinese etc)
deliver_at  | datetime | The scheduled date and time of the message in RFC3339 format (Y-m-d H:i:s)

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Check Balance

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
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

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Check Delivery Status

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

