# http\Client http\Client::setDebug(callable $callback)

Set client debugging callback.

> ***NOTE:***
> This method has been added in v2.6.0, resp. v3.1.0.

## Params:

* callable $callback as function(http\Client $c, http\Client\Request $r, int $type, string $data)  
  The debug callback. For $type see http\Client::DEBUG_* constants.

## Returns:

* http\Client, self.

## Throws:

* http\Exception\InvalidArgumentException

## Example:

	<?php

	(new http\Client)->setDebug(function($c, $r, $type, $data) {
		if ($type === http\Client::DEBUG_INFO) {
			printf("INFO: %s\n", $data);
		} else {
			repeat:
			if ($type & http\Client::DEBUG_OUT) {
				$sep = ">";
			} elseif ($type & http\Client::DEBUG_IN) {
				$sep = "<";
			}
			if ($type & http\Client::DEBUG_SSL) {
				printf("%s <%d bytes of SSL data>\n", $sep, strlen($data));
			} else {
				printf("%s %s\n", $sep, str_replace("\n", "\n$sep ", rtrim($data, "\n")));
			}
		}
	})->enqueue(new http\Client\Request("GET", "http://example.com"))->send();

	?>

> ***NOTE:***
> Except for http\Client::DEBUG_INFO, which always occurs separately, the debug
> callback's $type argument contains a bitmask of (http\Client::DEBUG_IN or http\Client::DEBUG_OUT)
> and (http\Client::DEBUG_HEADER or http\Client::DEBUG_BODY or http\Client::DEBUG_SSL).

### Yields:

	INFO:   Trying 93.184.216.34...

	INFO: Connected to example.com (93.184.216.34) port 80 (#0)

	> GET / HTTP/1.1
	> Host: example.com
	> User-Agent: PECL_HTTP/2.6.0dev PHP/5.6.19RC1 libcurl/7.50.0-DEV
	> Accept: */*
	>
	< HTTP/1.1 200 OK
	< Cache-Control: max-age=604800
	< Content-Type: text/html
	< Date: Thu, 18 Aug 2016 17:55:10 GMT
	< Etag: "359670651+gzip+ident"
	< Expires: Thu, 25 Aug 2016 17:55:10 GMT
	< Last-Modified: Fri, 09 Aug 2013 23:54:35 GMT
	< Server: ECS (iad/182A)
	< Vary: Accept-Encoding
	< X-Cache: HIT
	< x-ec-custom-error: 1
	< Content-Length: 1270
	<
	< <!doctype html>
	< <html>
	< <head>
	<     <title>Example Domain</title>
	<
	<     <meta charset="utf-8" />
	<     <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
	<     <meta name="viewport" content="width=device-width, initial-scale=1" />
	<     <style type="text/css">
	<     body {
	<         background-color: #f0f0f2;
	<         margin: 0;
	<         padding: 0;
	<         font-family: "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
	<
	<     }
	<     div {
	<         width: 600px;
	<         margin: 5em auto;
	<         padding: 50px;
	<         background-color: #fff;
	<         border-radius: 1em;
	<     }
	<     a:link, a:visited {
	<         color: #38488f;
	<         text-decoration: none;
	<     }
	<     @media (max-width: 700px) {
	<         body {
	<             background-color: #fff;
	<         }
	<         div {
	<             width: auto;
	<             margin: 0 auto;
	<             border-radius: 0;
	<             padding: 1em;
	<         }
	<     }
	<     </style>
	< </head>
	<
	< <body>
	< <div>
	<     <h1>Example Domain</h1>
	<     <p>This domain is established to be used for illustrative examples in documents. You may use this
	<     domain in examples without prior coordination or asking for permission.</p>
	<     <p><a href="http://www.iana.org/domains/example">More information...</a></p>
	< </div>
	< </body>
	< </html>
	INFO: Connection #0 to host example.com left intact
