# namespace http\Client\Curl

The http\Client\Curl namespace holds option value constants specific to the curl driver of the http\Client.

Head down for the [list of available request options](http/Client/Curl#Options:) as well as the 
[list of available client configuration options](http/Client/Curl#Configuration:).

## Constants:

### Features and Versions

* FEATURES  
  Bitmask of available libcurl features.  
  See http\Client\Curl\Features namespace.
* VERSIONS  
  List of library versions of or linked into libcurl,  
  e.g. "libcurl/7.50.0 OpenSSL/1.0.2h zlib/1.2.8 libidn/1.32 nghttp2/1.12.0".  
  See http\Client\Curl\Versions namespace.

### HTTP Protocol Version

* HTTP_VERSION_1_0  
  Use HTTP/1.0 protocol version.
* HTTP_VERSION_1_1  
  Use HTTP/1.1 protocol version.
* HTTP_VERSION_2_0  
  Attempt to use HTTP/2 protocol version. Available if libcurl is v7.33.0 or more recent and was built with nghttp2 support.
* HTTP_VERSION_2TLS  
  Attempt to use version 2 for HTTPS, version 1.1 for HTTP. Available if libcurl is v7.47.0 or more recent and was built with http2 support.
* HTTP_VERSION_2_PRIOR_KNOWLEDGE  
  Declare prior knowledge that the server supports plain (non-TLS) HTTP/2. Available if libcurl is v7.49.0 or more recent and was built with http2 support.
* HTTP_VERSION_3  
  Force usage of HTTP/3. See also http\Client\Curl::$altsvc. Available if libcurl is v7.66.0 or more recent.
* HTTP_VERSION_ANY  
  Use any HTTP protocol version.
  
### SSL Protocol Version

* SSL_VERSION_TLSv1_0  
  Use TLS v1.0 encryption. Available if libcurl is v7.34.0 or more recent.
* SSL_VERSION_TLSv1_1  
  Use TLS v1.1 encryption. Available if libcurl is v7.34.0 or more recent.
* SSL_VERSION_TLSv1_2  
  Use TLS v1.2 encryption. Available if libcurl is v7.34.0 or more recent.
* SSL_VERSION_TLSv1_3  
  Use TLS v1.3 encryption. Available if libcurl is v7.52.0 or more recent.
* SSL_VERSION_TLSv1  
  Use any TLS v1 encryption.
* SSL_VERSION_SSLv2  
  Use SSL v2 encryption.
* SSL_VERSION_SSLv3  
  Use SSL v3 encryption.
* SSL_VERSION_ANY  
  Use any encryption.
* SSL_VERSION_MAX_DEFAULT  
  Use max default encryption. To be bitwise ORed to a http\Client\Curl\SSL_VERSION_ constant. Available if libcurl is v7.54.0 or more recent.
* SSL_VERSION_MAX_TLSv1_0  
  Use upt to TLS v1.0 encryption. To be bitwise ORed to a http\Client\Curl\SSL_VERSION_ constant. Available if libcurl is v7.54.0 or more recent.
* SSL_VERSION_MAX_TLSv1_1  
  Use up to TLS v1.1 encryption. To be bitwise ORed to a http\Client\Curl\SSL_VERSION_ constant. Available if libcurl is v7.54.0 or more recent.
* SSL_VERSION_MAX_TLSv1_2  
  Use up to TLS v1.2 encryption. To be bitwise ORed to a http\Client\Curl\SSL_VERSION_ constant. Available if libcurl is v7.54.0 or more recent.
* SSL_VERSION_MAX_TLSv1_3  
  Use up to TLS v1.3 encryption. To be bitwise ORed to a http\Client\Curl\SSL_VERSION_ constant. Available if libcurl is v7.54.0 or more recent.

### TLS Auth Types

* TLSAUTH_SRP  
  Use TLS SRP authentication. Available if libcurl is v7.21.4 or more recent and was built with gnutls or openssl with TLS-SRP support.

### DNS IP Version

* IPRESOLVE_V4  
  Use IPv4 resolver.
* IPRESOLVE_V6  
  Use IPv6 resolver.
* IPRESOLVE_ANY  
  Use any resolver.

### Authentication Type

* AUTH_NONE  
  Don't use authentication.
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
* AUTH_BEARER  
  Bearer authentication. Set bearer with http\Client\Curl::$xoauth2_bearer request option. Available if libcurl is v7.61.0 or more recent.
* AUTH_AWS_SIGV4  
  Use AWS SIGv4 authentication. Available if libcurl is v7.75.0 or more recent.
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

### Alt-Svc Cache Control

* ALTSVC_READONLYFILE  
  Do only read from but not write to the Alt-Svc cache file. Available if libcurl is v7.64.1 or more recent.
* ALTSVC_H1  
  Accept alternative services offered over HTTP/1.1. Available if libcurl is v7.64.1 or more recent.
* ALTSVC_H2  
  Accept alternative services offered over HTTP/2. Available if libcurl is v7.64.1 or more recent.
* ALTSVC_H3  
  Accept alternative services offered over HTTP/3. Available if libcurl is v7.64.1 or more recent.

### HSTS Cache Control

* HSTS_ENABLE  
  Enable the cache. Available if libcurl is v7.74.0 or more recent.
* HSTS_READONLYFILE  
  Do only read from but not write to the HSTS cache file. Available if libcurl is v7.74.0 or more recent.

## Options:

The option names used here are more or less derived from the corresponding CURLOPT_* names.
### HTTP

* int $protocol  
  The HTTP protocol version. See http\Client\Curl\HTTP_VERSION_* constants.
* bool $http09_allowed  
  Allow HTTP/0.9 responses. Available if libcurl is v7.64.0 or more recent. Prior to v7.64.0, responses without headers were treated as HTTP/0.9 responses and uncoditionally allowed. Enable this option to restore that behavior.

### Proxies

* string $proxyhost  
  The hostname of the proxy.
* int $proxytype  
  See http\Client\Curl\PROXY_* constants.
* int $proxyport  
  The port number of the proxy.
* string $proxyauth  
  user:password
* int $proxyauthtype  
  See http\Client\Curl\AUTH_* constants.
* bool $proxytunnel  
  Tunnel all operations through the proxy.
* string $noproxy  
  Comma separated list of hosts where no proxy should be used. Available if libcurl is v7.19.4 or more recent.
* array $proxyheader  
  List of key/value pairs of headers which should only be sent to a proxy. Available if libcurl is v7.37.0 or more recent.
* string $proxy_service_name  
  Proxy service name. The default service name is "HTTP" for HTTP based proxies and "rcmd" for SOCKS5. Available if libcurl is v7.43.0 or more recent and has built-in GSSAPI support.
* int $socks5_auth  
  SOCKS5 proxy authentication type. Available if libcurl is v7.55.0 or more recent.  
  Available settings:  
  * http\Client\Curl\AUTH_NONE
  * http\Client\Curl\AUTH_BASIC
  * http\Client\Curl\AUTH_GSSNEG
* bool $haproxy_protocol  
  Send special [HAProxy protocol](https://github.com/haproxy/haproxy/blob/master/doc/proxy-protocol.txt) preamble. Available if libcurl is v7.60.0 or more recent.

### DNS

* int $dns_cache_timeout  
  Resolved hosts will be kept fot this number of seconds.
* int $ipresolve  
  See http\Client\Curl\IPRESOLVE_* constants.
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
* bool $dns_shuffle_addresses  
  Enforce shuffling DNS addresses returned from the system. Available if libcurl is v7.60.0 or more recent.
* string $doh_url  
  URL to use for DNS-over-HTTPS. Note the HTTPS. Available if libcurl is v7.62.0 or more recent.
  
### Limits

* int $low_speed_limit  
  Minimum speed in bytes per second.
* int $low_speed_time  
  Maximum time in seconds the transfer can be below $low_speed_limit before cancelling.
* int $maxfilesize  
  Maximum download size.
* int $maxage_conn  
  Maximum time in seconds an idle connection is checked to still be alive for a new transfer. Defaults to 118 seconds. Available if libcurl is v7.65.0 or more recent.

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
* bool $tcp_fastopen  
  Enable [TCP Fast Open](http://tools.ietf.org/html/rfc7413) on supported platforms.
* string $unix_socket_path  
  Connect to the webserver listening at $unix_socket_path instead of opening a TCP connection to it. Available if libcurl is v7.40.0 or more recent and has built-in unix socket support.
* string $abstract_unix_socket  
  Similar to $unix_socket_path but for abstract namespaces independent of the filesystem. The preceding NULL byte is adedd automatically. Available if libcurl is v7.53.0 on supporting platforms and has built-in unix socket support.
* bool $path_as_is  
  Do *not* squash sequences of "/../" or "/./" that may exist in the URL's path.

### Authentication

* string $httpauth  
  user:password
* int $httpauthtype  
  See http\Client\Curl\AUTH_* constants.
* string $service_name  
  The name of the service for DIGEST-MD5, SPNEGO and KERBEROS5 authentication mechanisms. The default service name is "HTTP". Available if libcurl is v7.43.0 or more recent.
* string $xoauth2_bearer  
  Bearer token for http\Client\Curl\AUTH_BEARER. Available if libcurl is v7.61.0 or more recent.
* string $aws_sigv4  
  Provide AWS V4 signature authentication in the form of `provider1[:provider2[:region[:service]]]`. Defaults to `aws:amz` if http\Client\Curl\AUTH_AWS_SIGV4 was used for $httpauthtype. Available if libcurl is v7.75.0 or more recent.

### Redirection

* int $redirect  
  How many redirects to follow.
* bool $unrestricted_auth  
  Whether to keep sending authentication credentials on redirects to different hosts.
* int $postredir  
  See http\Client\Curl\POSTREDIR_* constants. Available if libcurl is v7.19.1 or more recent.

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
  Custom User-Agent header. Setting this option to NULL will use the default user agent, use the empty string to prevent this header being sent at all.
* string $etag  
  Custom ETag.
* bool $compress  
  Whether to request compressed content (through Accept-Encoding).
* int $lastmodified  
  Custom If-(Un)Modified since time. If less than zero, the current time will be added.
* string $altsvc  
  Specify a file name to use as `Alt-Svc` cache. Available if libcurl is v7.64.1 or more recent.
* int $altsvc_ctrl  
  Specify how to handle `Alt-Svc` announcements as a bitmask of http\Client\Curl\ALTSVC_* constants. Available if libcurl is v7.64.1 or more recent.
* string $hsts  
  Specify a file name to use as HSTS cache. Availalbe if libcurl is v7.74.0 or more recent.
* int $hsts_ctrl  
  Specify how to handle the HSTS cache as a bitmask of http\Client\Curl\HSTS_* constatns. Available if libcurl is v7.74.0

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
    See http\Client\Curl\SSL_VERSION_* constants.
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
    CA PEM cert file for peer verification. Available if libcurl is v7.19.0 or more recent.
  * string $crlfile  
    File with the concatenation of CRL in PEM format. Available if libcurl was built with OpenSSL support.
  * bool $certinfo  
    Enable gathering of SSL certificate chain information. Available if libcurl is v7.19.1 or more recent.
  * string $pinned_publickey  
    File with a public key to pin. Available if libcurl is v7.39.0 or more recent.
  * int $tlsauthtype  
    TLS_AUTH_* constant. Available if libcurl is v7.21.4 or more recent.
  * string $tlsauthuser  
    TLS-SRP username. Available if libcurl is v7.21.4 or more recent.
  * string $tlsauthpass  
    TLS-SRP password. Available if libcurl is v7.21.4 or more recent.
  * bool $verifystatus  
    Enable OCSP. Available if libcurl is v7.41.0 or more recent and was built with OpenSSL, GnuTLS or NSS support.
  * bool $falsestart  
    Whether false start should be used during the TLS handshake. Available if libcurl is v7.42.0 or more recent and was built with NSS or SecureTransport support.
  * string $tls13_ciphers  
    TLSv1.3 cipher list. Available if libcurl is v7.61.0 or more recent.
* array $proxy_ssl  
  Subarray of SSL related options to use for the proxy:  
  > See the respective $ssl options above for descriptions.  

  * string $cert  
    Available if libcurl is v7.52.0 or more recent.
  * string $certtype  
    Available if libcurl is v7.52.0 or more recent.
  * string $key  
    Available if libcurl is v7.52.0 or more recent.
  * string $keytype  
    Available if libcurl is v7.52.0 or more recent.
  * string $keypasswd  
    Available if libcurl is v7.52.0 or more recent.
  * int $version  
    Available if libcurl is v7.52.0 or more recent.
  * bool $verifypeer  
    Available if libcurl is v7.52.0 or more recent.
  * bool $verifyhost  
    Available if libcurl is v7.52.0 or more recent.
  * string $cipher_list  
    Available if libcurl is v7.52.0 or more recent.
  * string $cainfo  
    Available if libcurl is v7.52.0 or more recent.
  * string $capath  
    Available if libcurl is v7.52.0 or more recent.
  * string $crlfile  
    Available if libcurl is v7.52.0 or more recent.
  * string $pinned_publickey  
    Available if libcurl is v7.52.0 or more recent.
  * int $tlsauthtype  
    Available if libcurl is v7.52.0 or more recent.
  * string $tlsauthuser  
    Available if libcurl is v7.52.0 or more recent.
  * string $tlsauthpass  
    Available if libcurl is v7.52.0 or more recent.
  * string $pinned_publickey  
    Available if libcurl is v7.59.0 or more recent.
  * string $tls13_ciphers  
    Available if libcurl is v7.61.0 or more recent.
  * string $issuercert  
    Available if libcurl is v7.71.0 or more recent.

## Configuration:

* int $maxconnects  
  Size of the connection cache.
* int $max_host_connections  
  Maximum number of connections to a single host. Available if libcurl is v7.30.0 or more recent.
* int $max_pipeline_length  
  Maximum number of requests in a pipeline. Available if libcurl is v7.30.0 or more recent.
* int $max_total_connections  
  Maximum number of simultaneous open connections of this client. Available if libcurl is v7.30.0 or more recent.
* int $max_concurrent_streams  
  Maximum count of simultanous streams to support over one HTTP/2 connection. Defaults to 100. Available if libcurl is v7.67.0 or more recent.
* bool $pipelining  
  Whether to enable HTTP/1.1 pipelining. Available if libcurl is **not** v7.62.0 or more recent.
* int $chunk_length_penalty_size  
  Chunk length threshold for pipelining; no more requests on this pipeline if exceeded. Available if libcurl is v7.30.0 or more recent, but less than v7.62.0.
* int $content_length_penalty_size  
  Size threshold for pipelining; no more requests on this pipeline if exceeded. Available if libcurl is v7.30.0 or more recent, but less than v7.62.0.
* array $pipelining_server_bl  
  Simple list of server software names to blacklist for pipelining. Available if libcurl is v7.30.0 or more recent, but less than v7.62.0.
* array $pipelining_site_bl  
  Simple list of server host names to blacklist for pipelining. Available if libcurl is v7.30.0 or more recent, but less than v7.62.0.
* mixed $use_eventloop  
  Whether to use an event loop. This option accepts either bool, whether to use
  the internal event loop, or an instance of an http\Client\Curl\User implementation.
  The internal event loop is only available if pecl/http was built with libevent support.
* bool $share_cookies  
  Whether to let the client share cookies between requests.
* bool $share_ssl  
  Whether to let the client share SSL/TLS sessions between requests. Available if libcurl is v7.23.0 or more recent.
