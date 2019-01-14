## **Definition and Usage**
The `cURLit()` executes a set of parameters over to a URL with headers and all.

## Usage
```
<?php
echo cURLit('https://example.com', array(
    'method' => 'POST',
    'headers' => array(),
    'body' => array(),
    'basic_auth' => 'user123:secretPhrase'
), 'json_decode');
```

## Syntax
```
cURLit(url, options, output)
```
| Parameter | Type   | Description |
| --------- | ------ | ----------- |
| url       | string | Required - URL to be fetched |
| options   | array  | Optional - Set of array with keys: `method`, `headers`, `json`, `body`, `basic_auth`, `user_agent`, `proxy_addr`, `proxy_auth`. Default: array() |
| output    | string | Optional - Output the type of response received from the Server. It can be `options`, `error`, `curl_info`, `response`, `header`, `body`,  `json_decode`, `all`. Default: body |

#### &raquo;&raquo; Options
Optional. Here are list of keys that you can use for options.

| Key        | Type   | Description |
| ---------- | ------ | ----------- |
| method     | string | **Default: GET**. Methods for more obscure HTTP requests. Valid values are like `GET`, `POST`, `CONNECT`, `DELETE` and so on.|
| header     | array  | Set of Headers |
| json       | array or string | JSON data will be encoded automatically. It will add Header - `Content-Type: application/json` |
| body       | array or string | HTTP query will be built automatically. It will add `Content-Type: application/x-www-form-urlencoded` |
| basic_auth | string | Specify the user name and password to use for server authentication. Syntax: `USERNAME:PASSWORD`|
| user_agent | string | User-Agent string to identify the application type, operating system, software vendor or software version of the requesting software user agent.|
| proxy_addr | string | Proxy Host and Port that does something on behalf of you. Syntax: `HOST:PORT`|
| proxy_auth | string | Specify the user name and password to use for proxy authentication. Syntax: `USERNAME:PASSWORD`|

#### &raquo;&raquo; Output
Here are the list of return types available. By Default response body will be returned as usual.

| Key         | Description |
| ----------- | ----------- |
| options     | Option Parameters sent by user |
| error       | Display Error Message or `null` |
| curl_info   | Curl Information. [See Details](http://php.net/manual/en/function.curl-getinfo.php) |
| response    | Output Response after curl execution |
| header      | Output Header |
| body        | Output Body |
| json_decode | Decoded JSON data from response |
| all         | All Outputs|
