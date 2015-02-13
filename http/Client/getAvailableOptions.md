# array http\Client::getAvailableOptions()

Retrieve a list of available request options and their default values.

See f.e. the [request options for the Curl driver](http/Client/Curl#Options:).

## Params:

None.

## Returns:

* array, list of key/value pairs of available request options and their default values.

## Throws:

* http\Exception\InvalidArgumentException

## Example:

	<?php
	
	$client = new http\Client("curl");
	var_dump($client->getAvailableOptions());
	
	?>

Yields:

	array(49) {
	  ["proxyhost"]=>
	  NULL
	  ["proxytype"]=>
	  int(0)
	  ["proxyport"]=>
	  int(0)
	  ["proxyauth"]=>
	  NULL
	  ["proxyauthtype"]=>
	  int(-18)
	  ["proxytunnel"]=>
	  bool(false)
	  ["noproxy"]=>
	  NULL
	  ["proxyheader"]=>
	  NULL
	  ["unix_socket_path"]=>
	  NULL
	  ["dns_cache_timeout"]=>
	  int(60)
	  ["ipresolve"]=>
	  int(0)
	  ["resolve"]=>
	  NULL
	  ["low_speed_limit"]=>
	  int(0)
	  ["low_speed_time"]=>
	  int(0)
	  ["fresh_connect"]=>
	  bool(false)
	  ["forbid_reuse"]=>
	  bool(false)
	  ["interface"]=>
	  NULL
	  ["portrange"]=>
	  NULL
	  ["port"]=>
	  int(0)
	  ["address_scope"]=>
	  int(0)
	  ["httpauth"]=>
	  NULL
	  ["httpauthtype"]=>
	  int(-18)
	  ["redirect"]=>
	  int(0)
	  ["unrestricted_auth"]=>
	  bool(false)
	  ["postredir"]=>
	  int(0)
	  ["retrycount"]=>
	  int(0)
	  ["retrydelay"]=>
	  float(0)
	  ["referer"]=>
	  NULL
	  ["autoreferer"]=>
	  bool(true)
	  ["useragent"]=>
	  string(51) "PECL_HTTP/2.3.0dev PHP/5.6.6-dev libcurl/7.41.0-DEV"
	  ["resume"]=>
	  int(0)
	  ["range"]=>
	  NULL
	  ["etag"]=>
	  NULL
	  ["compress"]=>
	  bool(false)
	  ["lastmodified"]=>
	  int(0)
	  ["encodecookies"]=>
	  bool(true)
	  ["cookies"]=>
	  NULL
	  ["cookiesession"]=>
	  bool(false)
	  ["cookiestore"]=>
	  NULL
	  ["maxfilesize"]=>
	  int(0)
	  ["protocol"]=>
	  int(0)
	  ["timeout"]=>
	  float(0)
	  ["connecttimeout"]=>
	  float(3)
	  ["expect_100_timeout"]=>
	  float(1)
	  ["tcp_nodelay"]=>
	  bool(false)
	  ["tcp_keepalive"]=>
	  bool(false)
	  ["tcp_keepidle"]=>
	  int(60)
	  ["tcp_keepintvl"]=>
	  int(60)
	  ["ssl"]=>
	  array(24) {
		["cert"]=>
		NULL
		["certtype"]=>
		string(3) "PEM"
		["key"]=>
		NULL
		["keytype"]=>
		string(3) "PEM"
		["keypasswd"]=>
		NULL
		["engine"]=>
		NULL
		["version"]=>
		int(0)
		["verifypeer"]=>
		bool(true)
		["verifyhost"]=>
		bool(true)
		["verifystatus"]=>
		bool(false)
		["cipher_list"]=>
		NULL
		["cainfo"]=>
		string(34) "/etc/ssl/certs/ca-certificates.crt"
		["capath"]=>
		NULL
		["random_file"]=>
		NULL
		["egdsocket"]=>
		NULL
		["issuercert"]=>
		NULL
		["crlfile"]=>
		NULL
		["certinfo"]=>
		bool(false)
		["enable_npn"]=>
		bool(true)
		["enable_alpn"]=>
		bool(true)
		["pinned_publickey"]=>
		NULL
		["tlsauthtype"]=>
		int(0)
		["tlsauthuser"]=>
		NULL
		["tlsauthpass"]=>
		NULL
	  }
	}

