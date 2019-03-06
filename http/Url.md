# class http\Url

The http\Url class provides versatile means to parse, construct and manipulate URLs.

## Constants:

* REPLACE  
  Replace parts of the old URL with parts of the new.
* JOIN_PATH  
  Whether a relative path should be joined into the old path.
* JOIN_QUERY  
  Whether the querystrings should be joined.
* STRIP_USER  
  Strip the user information from the URL.
* STRIP_PASS  
  Strip the password from the URL.
* STRIP_AUTH  
  Strip user and password information from URL (same as STRIP_USER|STRIP_PASS).
* STRIP_PORT  
  Do not include the port.
* STRIP_PATH  
  Do not include the URL path.
* STRIP_QUERY  
  Do not include the URL querystring.
* STRIP_FRAGMENT  
  Strip the fragment (hash) from the URL.
* STRIP_ALL  
  Strip everything except scheme and host information.
* FROM_ENV  
  Import initial URL parts from the SAPI environment.
* SANITIZE_PATH  
  Whether to sanitize the URL path (consolidate double slashes, directory jumps etc.)
* PARSE_MBUTF8  
  Parse UTF-8 encododed multibyte sequences.
* PARSE_MBLOC  
  Parse locale encoded multibyte sequences (on systems with wide character support).
* PARSE_TOIDN  
  Parse and convert multibyte hostnames according to IDNA (with IDNA support).
* PARSE_TOIDN_2003  
  Explicitly request IDNA2003 implementation if available (libidn, idnkit or ICU).
* PARSE_TOIDN_2008  
  Explicitly request IDNA2008 implementation if available (libidn2, idnkit2 or ICU).
* PARSE_TOPCT  
  Percent encode multibyte sequences in the userinfo, path, query and fragment parts of the URL.
* IGNORE_ERRORS  
  Continue parsing when encountering errors.
* SILENT_ERRORS  
  Suppress errors/exceptions.
* STDFLAGS  
  Standard flags used by default internally for e.g. http\Message::setRequestUrl().
  Enables joining path and query, sanitizing path, multibyte/unicode, international domain names and transient percent encoding.

## Properties:

* public string $scheme = NULL  
  The URL's scheme.
* public string $user = NULL  
  Authenticating user.
* public string $pass = NULL  
  Authentication password.
* public string $host = NULL  
  Hostname/domain.
* public string $port = NULL  
  Port.
* public string $path = NULL  
  URL path.
* public string $query = NULL  
  URL querystring.
* public string $fragment = NULL  
  URL fragment (hash).
