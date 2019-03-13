# pecl/http

## About:

Extended HTTP support. Again.

* Introduces the http namespace.
* PHP stream based message bodies.
* Encapsulated env request/response.
* Modular client support.

## Installation:

This extension is hosted at [PECL](http://pecl.php.net) and can be installed with [PEAR](http://pear.php.net)'s pecl command:

    # pecl install pecl_http

## Dependencies:

pecl/http depends on a number of system libraries and PHP extensions for special features.

#### Required system libraries:

The following system libraries are required to build this extension:

=zlib=
	Provides gzip/zlib/deflate encoding.  
	Configure: `--with-http-zlib-dir`  
	Minimum version: 1.2.0.4  
	Install on Debian: `apt-get install zlib1g-dev`


#### Optional system libraries:

The following system libraries are optional and provide additional features:

=libcurl=
	Provides HTTP request functionality.  
	Configure: `--with-http-libcurl-dir`  
	Minimum version: 7.18.2  
	Install on Debian: `apt-get install libcurl4-openssl-dev`  

=libbrotli=
	Provides brotli encoding.  
	Configure: `--with-http-libbrotli-dir`  
	Minimum version: 1.0  
	Install on Debian: `apt-get install libbrotli-dev`  
 
=libevent=
	Internal event loop support for the HTTP client.  
	Configure: `--with-http-libevent-dir`  
	Minimum version: none  
	Install on Debian: `apt-get install libevent-dev`

=libicu=
	Provides IDNA2003 and/or IDNA2008 support in URLs.  
	Configure: `--with-http-libicu-dir`  
	Minimum version: none  
	Install on Debian: `apt-get install libicu-dev`

=libidn=
	Provides IDNA2003 support in URLs.  
	Configure: `--with-http-libidn-dir`  
	Minimum version: none  
	Install on Debian: `apt-get install libidn11-dev`

=libidn2=
	Provides IDNA2008 support in URLs.  
	Configure: `--with-http-libidn2-dir`  
	Minimum version: none  
	Install on Debian: `apt-get install libidn2-0-dev`

=libidnkit=
	Provides IDNA2003 support in URLs. Conflicts with libidnkit2.  
	Configure: `--with-http-libidnkit-dir`  
	Minimum version: none  
	Install on Debian: N/A

=libidnkit2=
	Provides IDNA2008 support in URLs. Conflicts with libidnkit.  
	Configure: `--with-http-libidnkit2-dir`  
	Minimum version: none  
	Install on Debian: N/A

##### A note on IDNA libraries:

If configured with multiple IDNA libraries' support, there's a run-time precedence of ICU over GNU libidn, which in turn has precendence over idnkit. If neither IDNA2008, nor IDNA2003 is explicitly requested, IDNA2008 has precendence.

##### A note on the CURL library:

There are usually different styles of SSL support for libcurl available, so you can choose between 'openssl' and f.e. 'nss' or 'gnutls' when installing libcurl.

### PHP extensions:

This extension unconditionally depends on the pre-loaded presence of the following PHP extensions:

* raphf
* propro
* spl


If configured ```--with-http-shared-deps``` (default) it depends on the pre-loaded presence of the following extensions, as long as they were available at build time:

* hash
* iconv
* json (only until < 2.4.0)

Please ensure that all extension on which pecl/http depends, are loaded before it, e.g in your `php.ini`:

	; obligatory deps
	extension = raphf.so
	extension = propro.so

	; if shared deps were enabled
	extension = hash.so
	extension = iconv.so
	extension = json.so

	; finally load pecl/http
	extension = http.so

## Conflicts:

pecl/http-v2 conflicts with the following extensions:

* http-v1
* event (only until <= 2.0.3)

## INI Directives:

* http.etag.mode = "crc32b"  
  Default hash method for dynamic response payloads to generate an ETag.

## Stream Filters:

The http extension registers the ```http.*``` namespace for its stream filters. Provided stream filters are:

* http.chunked_decode  
  Decode a stream encoded with chunked transfer encoding.
* http.chunked_encode  
  Encode a stream with chunked transfer encoding.
* http.inflate  
  Decode a stream encoded with deflate/zlib/gzip encoding.
* http.deflate  
  Encode a stream with deflate/zlib/gzip encoding.

## Changelog:

0. v2.0.4
	* Dropped the pecl/event conflict.
0. v2.4.0
	* Dropped the ext/json dependency.
0. v2.4.2
	* Added libidn2 and libicu as fallback for IDNA support.
0. v2.6.0, v3.1.0
	* Added idnkit-1 IDNA2003 support.
	* Added idnkit-2 IDNA2008 support.
	* Added ICU IDNA2008 support.
	* Added explicit configuration options for each IDNA library.
0. v3.2.0
	* Added brotli encoding support.
