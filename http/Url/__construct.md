# void http\Url::__construct([mixed $old_url = NULL[, mixed $new_url = NULL[, int $flags = 0]]])

Create an instance of an http\Url.

> ***NOTE:***
> Prior to v3.0.0, the default for the $flags parameter was http\Url::FROM_ENV.

See also http\Env\Url.

## Params:

* Optional mixed $old_url = NULL  
  Initial URL parts. Either an array, object, http\Url instance or string to parse.
* Optional mixed $new_url = NULL  
  Overriding URL parts. Either an array, object, http\Url instance or string to parse.
* Optional int $flags = 0  
  The modus operandi of constructing the url. See http\Url constants.

## Throws:

* http\Exception\InvalidArgumentException
* http\Exception\BadUrlException

## Changelog:

0. v3.0.0
	* Changed the default of the $flags parameter from http\Url::FROM_ENV to 0.
