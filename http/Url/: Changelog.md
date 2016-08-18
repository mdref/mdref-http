# http\Url Changelog

0. v2.2.0
	* Added parser constants:
		* http\Url::PARSE_MBUTF8
		* http\Url::PARSE_MBLOC (on systems with wide character support)
		* http\Url::PARSE_TOIDN (with libidn support)
		* http\Url::PARSE_TOPCT

## Backwards compatibility notes

### New parser in v2.2.0

PHP's [parse_url()](http://php.net/parse_url) is avoided since v2.2.0.

Creating an empty url by `new http\Url(NULL, NULL, 0)` will not result in `http://localhost/` anymore but in an empty URL instead.

### No more default parts from the environment in v3.0.0

The default value of the $flags parameter of http\Url::__construct() was changed from http\Url::FROM_ENV to 0 and http\Env\Url was introduced instead.