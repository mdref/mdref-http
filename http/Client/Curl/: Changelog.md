# http\Client\Curl Changelog

0. v2.1.0
	* Added request options:
		* $dns_interface
		* $dns_local_ip4
		* $dns_local_ip6
		* $expect_100_timeout
0. v2.1.2
	* Added request option constants:
		* http\Client\Curl\POSTREDIR_303
		* http\Client\Curl\AUTH_SPNEGO
		* http\Client\Curl\SSL_VERSION_TLSv1_0
		* http\Client\Curl\SSL_VERSION_TLSv1_1
		* http\Client\Curl\SSL_VERSION_TLSv1_2
0. v2.3.0
	* Added request options:
		* $proxyheader
		* $unix_socket_path
	* Added SSL request options:
		* $pinned_publickey
		* $tlsauth
		* $verifystatus
	* Added request option constants:
		* http\Client\Curl\HTTP_VERSION_2_0
		* http\Client\Curl\TLS_AUTH_SRP
0. v2.5.1
	* Added request options:
		* $proxy_service_name
		* $service_name
	* Added SSL request options:
		* $falsestart
0. v2.5.6
	* Added request option constants:
		* http\Client\Curl\HTTP_VERSION_2TLS
0. v2.6.0, v3.1.0
	* Added methods:
		* http\Client::setDebug()
	* Added client configure options:
		* $share_cookies
		* $share_ssl
	* Changed client configure options:
		* bool $use_eventloop changed to mixed to accept an http\Client\Curl\User implementation
	* Added constants:
		* http\Client\Curl::FEATURES
		* http\Client\Curl::VERSIONS
	* Added namespaces:
		* http\Client\Curl\Features
		* http\Client\Curl\Versions
	* Added interfaces:
		* http\Client\Curl\User
