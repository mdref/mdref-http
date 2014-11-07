# namespace http\Client\Curl

The http\Client\Curl namespace holds option value constants specific to the curl driver of the http\Client.

## Changelog

Version | Change
--------|-------
2.1.0   | Added $dns_interface, $dns_local_ip4, $dns_local_ip6 options, $expect_100_timeout.
2.1.2   | Added request option constants:<br> http\Client\Curl::POSTREDIR_303,<br> http\Client\Curl::AUTH_SPNEGO,<br> http\Client\Curl::SSL_VERSION_TLSv1_0,<br> http\Client\Curl::SSL_VERSION_TLSv1_1 and<br> http\Client\Curl::SSL_VERSION_TLSv1_2 

## Constants:

### HTTP Protocol Version

* HTTP_VERSION_1_0  
  Use HTTP/1.0 protocol version.
* HTTP_VERSION_1_1  
  Use HTTP/1.1 protocol version.
* HTTP_VERSION_ANY  
  Use any HTTP protocol version.
  
### SSL Protocol Version

* SSL_VERSION_TLSv1_0  
  Use TLS v1.0 encryption.
* SSL_VERSION_TLSv1_1  
  Use TLS v1.1 encryption.
* SSL_VERSION_TLSv1_2  
  Use TLS v1.2 encryption.
* SSL_VERSION_TLSv1  
  Use any TLS v1 encryption.
* SSL_VERSION_SSLv2  
  Use SSL v2 encryption.
* SSL_VERSION_SSLv3  
  Use SSL v3 encryption.
* SSL_VERSION_ANY  
  Use any encryption.

### DNS IP Version

* IPRESOLVE_V4  
  Use IPv4 resolver.
* IPRESOLVE_V6  
  Use IPv6 resolver.
* IPRESOLVE_ANY  
  Use any resolver.

### Authentication Type

* AUTH_BASIC  
  Use Basic authentication.
* AUTH_DIGEST  
  Use Digest authentication.
* AUTH_DIGEST_IE  
  Use IE (lower v7) quirks with Digest authentication. Available if libcurl is v7.19.3 or more recent.
* AUTH_NTLM  
  Use NTLM authentication.
* AUTH_GSSNEG  
  Use GSS-Negotiate authentication.
* AUTH_SPNEGO  
  Use HTTP Netgotiate authentication (SPNEGO, RFC4559). Available if libcurl is v7.38.0 or more recent.
* AUTH_ANY  
  Use any authentication.

### Proxy Protocol Version

* PROXY_SOCKS4  
  Use SOCKSv4 proxy protocol.
* PROXY_SOCKS4A  
  Use SOCKSv4a proxy protocol.
* PROXY_SOCKS5_HOSTNAME  
  Use SOCKS5h proxy protocol.
* PROXY_SOCKS5  
  Use SOCKS5 proxy protoccol.
* PROXY_HTTP  
  Use HTTP/1.1 proxy protocol.
* PROXY_HTTP_1_0  
  Use HTTP/1.0 proxy protocol. Available if libcurl is v7.19.4 or more recent.

### POST Redirection Behavior

* POSTREDIR_301  
  Keep POSTing on 301 redirects. Available if libcurl is v7.19.1 or more recent.
* POSTREDIR_302  
  Keep POSTing on 302 redirects. Available if libcurl is v7.19.1 or more recent.
* POSTREDIR_303  
  Keep POSTing on 303 redirects. Available if libcurl is v7.19.1 or more recent.
* POSTREDIR_ALL  
  Keep POSTing on any redirect. Available if libcurl is v7.19.1 or more recent.


## Options:

The option names used here are more or less derived from the corresponding CURLOPT_* names.
### HTTP

* int $protocol  
  The HTTP protocol version. See http\Client\Curl::HTTP_VERSION_* constants.

### Proxies

* string $proxyhost  
  The hostname of the proxy.
* int $proxytype  
  See http\Client\Curl::PROXY_* constants.
* int $proxyport  
  The port number of the proxy.
* string $proxyauth  
  user:password
* int $proxyauthtype  
  See http\Client\Curl::AUTH_* constants.
* bool $proxytunnel  
  Tunnel all operations through the proxy.
* string $noproxy  
  Comma separated list of hosts where no proxy should be used. Available if libcurl is v7.19.4 or more recent.

### DNS

* int $dns_cache_timeout  
  Resolved hosts will be kept fot this number of seconds.
* int $ipresolve  
  See http\Client\Curl::IPRESOLVE_* constants.
* array $resolve  
  A list of HOST:PORT:ADDRESS mappings which pre-populate the DNS cache. Available if libcurl is v7.21.3 or more recent.
* string $dns_servers  
  Comma separated list of custom DNS servers of the form HOST[:PORT]. Available if libcurl is v7.24.0 or more recent and has built-in c-ares support.
* string $dns_interface  
  The name of the network interface ***name*** that the DNS resolver should bind to. Available if libcurl is v7.33.0 or more recent and has built-in c-ares support.
* string $dns_local_ip4  
  The local IPv4 ***address*** that the resolver should bind to. Available if libcurl is v7.33.0 or more recent and has built-in c-ares support.
* string $dns_local_ip6  
  The local IPv6 ***address*** that the resolver should bind to. Available if libcurl is v7.33.0 or more recent and has built-in c-ares support.

### Limits

* int $low_speed_limit  
  Minimum speed in bytes per second.
* int $low_speed_time  
  Maximum time in seconds the transfer can be below $low_speed_limit before cancelling.
* int $maxfilesize  
  Maximum download size.

### Connection handling

* bool $fresh_connect  
  Force a new connection.
* bool $forbid_reuse  
  Force closing the connection.

### Networking

* string $interface  
  Outgoing interface name.
* array $portrange  
  A tuple of min/max ports.
* int $port  
  Override the URL's port.
* int $address_scope  
  RFC4007 zone_id. Available if libcurl is v7.19.0 or more recent.
* bool $tcp_keepalive  
  Whether to use TCP keepalive. Available if libcurl is v7.25.0 or more recent.
* int $tcp_keepidle  
  Seconds to wait before sending keepalive probes. Available if libcurl is v7.25.0 or more recent.
* int $tcp_keepintvl  
  Interval in seconds to wait between sending keepalive probes. Available if libcurl is v7.25.0 or more recent.
* bool $tcp_nodelay  
  Disable [Nagle's algotrithm](http://tools.ietf.org/html/rfc896).
  
### Authentication

* string $httpauth  
  user:password
* int $httpauthtype  
  See http\Client\Curl::AUTH_* constants.

### Redirection

* int $redirect  
  How many redirects to follow.
* bool $unrestricted_auth  
  Whether to keep sending authentication credentials on redirects to different hosts.
* int $postredir  
  See http\Client\Curl::POSTREDIR_* constants. Available if libcurl is v7.19.1 or more recent.

### Retries

* int $retrycount  
  Retry this often.
* float $retrydelay  
  Pause this number of seconds between retries.

### Special headers

* string $referer  
  Custom Referer header.
* bool $autoreferer  
  Whether to automatically send referers.
* string $useragent  
  Custom User-Agent header.
* string $etag  
  Custom ETag.
* bool $compress  
  Whether to request compressed content (through Accept-Encoding).
* int $lastmodified  
  Custom If-(Un)Modified since time. If less than zero, the current time will be added.

### Resume/Ranges

* int $resume  
  Resume from this byte offset.
* array $range  
  Fetch specific ranges (if server supports byte ranges).

### Cookies

* bool $encodecookies  
  Whether to URLencode cookies.
* array $cookies  
  List of custom cookies in the form ["name" => "value"].
* bool $cookiesession  
  Ignore previous session cookies to be loaded from $cookiestore.
* string $cookiestore  
  Path to a Netscape cookie file, from which cookies will be loaded resp. to which cookies will be written.

### Timeouts

* float $timeout  
  Seconds the complete transfer may take.
* float $connecttimeout  
  Seconds the connect may take.
* float $expect_100_timeout  
  Senconds to wait for the server to send a response to "Expect: 100-Continue" before just proceeding with the request. Available if libcurl is v7.36.0 or more recent.

### SSL

* array $ssl  
  Subarray of SSL related options:
  * string $cert  
    SSL certificate file.
  * string $certtype  
    Certificate type (DER, PEM). (Secure Transport additionally supports P12).
  * string $key  
    Private key file.
  * string $keytype  
    PK type (PEM, DER, ENG).
  * string $keypasswd  
    The password for the private key.
  * string $engine  
    Crypto engine to use for the private key.
  * int $version  
    See http\Client\Curl::SSL_VERSION_* constants.
  * bool $verifypeer  
    Whether to apply peer verification.
  * bool $verifyhost  
    Whether to apply host verification.
  * string $cipher_list  
    One or more cipher strings separated by colons.
  * string $cainfo  
    CA bundle to verify the peer with.
  * string $capath  
    Directory with prepared CA certs to verify the peer with.
  * string $random_file  
    A file used to read from to seed the random engine.
  * string $egdsocket  
    A Entropy Gathering Daemon socket.
  * string $issuercert  
    CA PEM cert for peer verification. Available if libcurl is v7.19.0 or more recent.
  * string $crlfile  
    File with the concatenation of CRL in PEM format. Available if libcurl was built with OpenSSL support.
  * bool $certinfo  
    Enable gathering of SSL certificate chain information. Available if libcurl is v7.19.1 or more recent.
