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
0. v4.1.0
	* Added request options:
		* http\Client\Curl::$abstract_unix_socket
		* http\Client\Curl::$altsvc
		* http\Client\Curl::$altsvc_ctrl
		* http\Client\Curl::$aws_sigv4
		* http\Client\Curl::$doh_url
		* http\Client\Curl::$dns_shuffle_addresses
		* http\Client\Curl::$haproxy_protocol
		* http\Client\Curl::$hsts
		* http\Client\Curl::$hsts_ctrl
		* http\Client\Curl::$http09_allowed
		* http\Client\Curl::$maxage_conn
		* http\Client\Curl::$pinned_publickey
		* http\Client\Curl::$proxy_ssl
		* http\Client\Curl::$socks5_auth
		* http\Client\Curl::$tcp_fastopen
		* http\Client\Curl::$tls13_ciphers
		* http\Client\Curl::$xoauth2_bearer
	* Added request option constants:
		* http\Client\Curl\AUTH_AWS_SIGV4
		* http\Client\Curl\AUTH_BEARER
		* http\Client\Curl\AUTH_NONE
		* http\Client\Curl\HTTP_VERSION_2_PRIOR_KNOWLEDGE
		* http\Client\Curl\HTTP_VERSION_3
		* http\Client\Curl\SSL_VERSION_MAX_*
		* http\Client\Curl\SSL_VERSION_TLSv1_3
	* Added library version constants:
		* http\Client\Curl\Versions\BROTLI
		* http\Client\Curl\Versions\CAINFO
		* http\Client\Curl\Versions\CAPATH
		* http\Client\Curl\Versions\HYPER
		* http\Client\Curl\Versions\ICONV
		* http\Client\Curl\Versions\NGHTTP2
		* http\Client\Curl\Versions\QUIC
		* http\Client\Curl\Versions\ZSTD
