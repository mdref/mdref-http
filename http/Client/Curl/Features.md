# namespace http\Client\Curl\Features

CURL feature constants.

> ***NOTE:***
> These constants have been added in v2.6.0, resp. v3.1.0.

## Constants:

* ASYNCHDNS  
  Whether libcurl supports asynchronous domain name resolution.
* GSSAPI  
  Whether libcurl supports the Generic Security Services Application Program Interface. Available if libcurl is v7.38.0 or more recent.
* GSSNEGOTIATE  
  Whether libcurl supports HTTP Generic Security Services negotiation.
* HTTP2  
  Whether libcurl supports the HTTP/2 protocol. Available if libcurl is v7.33.0 or more recent.
* IDN  
  Whether libcurl supports international domain names.
* IPV6  
  Whether libcurl supports IPv6.
* KERBEROS4  
  Whether libcurl supports the old Kerberos protocol.
* KERBEROS5  
  Whether libcurl supports the more recent Kerberos v5 protocol. Available if libcurl is v7.40.0 or more recent.
* LARGEFILE  
  Whether libcurl supports large files.
* LIBZ  
  Whether libcurl supports gzip/deflate compression.
* NTLM  
  Whether libcurl supports the NT Lan Manager authentication.
* NTLM_WB  
  Whether libcurl supports NTLM delegation to a winbind helper. Available if libcurl is v7.22.0 or more recent.
* PSL  
  Whether libcurl supports the Public Suffix List for cookie host handling. Available if libcurl is v7.47.0 or more recent.
* SPNEGO  
  Whether libcurl supports the Simple and Protected GSSAPI Negotiation Mechanism.
* SSL  
  Whether libcurl supports SSL/TLS protocols.
* SSPI  
  Whether libcurl supports the Security Support Provider Interface.
* TLSAUTH_SRP  
  Whether libcurl supports TLS Secure Remote Password authentication. Available if libcurl is v7.21.4 or more recent.
* UNIX_SOCKETS  
  Whether libcurl supports connections to unix sockets. Available if libcurl is v7.40.0 or more recent.
