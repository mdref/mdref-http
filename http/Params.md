# class http\Params implements ArrayAccess

Parse, interpret and compose HTTP (header) parameters.

## Changelog:

Version | Change
--------|-------
2.0.1   | Added [RFC5987](http://tools.ietf.org/html/rfc5987) support

## Example:

	<?php

	$u = urlencode("ü");
	$s = urlencode("ß");

	$t = "p1*=utf-8'de's$u$s,p2*=utf-8''hei$s;a1*=utf-8''a$s;a2*=utf-8''e$s;a3=no,p3=not";
	$p = new http\Params($t);

	var_dump($p->params, $p->toString());

	?>

Yields:

	array(3) {
		["p1"]=>
		array(2) {
			["*rfc5987*"]=>
			array(1) {
			  ["de"]=>
			  string(5) "süß"
			}
			["arguments"]=>
			array(0) {
			}
		}
		["p2"]=>
		array(2) {
			["*rfc5987*"]=>
			array(1) {
			  [""]=>
			  string(5) "heiß"
			}
			["arguments"]=>
			array(2) {
				["*rfc5987*"]=>
				array(2) {
				["a1"]=>
				array(1) {
				  [""]=>
				  string(3) "aß"
				}
				["a2"]=>
				array(1) {
				  [""]=>
				  string(3) "eß"
				}
				}
				["a3"]=>
				string(2) "no"
			}
		}
		["p3"]=>
		array(2) {
			["value"]=>
			string(3) "not"
			["arguments"]=>
			array(0) {
			}
		}
	}
	string(98) "p1*=utf-8'de's%C3%BC%C3%9F,p2*=utf-8''hei%C3%9F;a1*=utf-8''a%C3%9F;a2*=utf-8''e%C3%9F;a3=no,p3=not"


## Constants:

* DEF_PARAM_SEP  
  The default parameter separator (",").
* DEF_ARG_SEP  
  The default argument separator (";").
* DEF_VAL_SEP  
  The default value separator ("=").
* COOKIE_PARAM_SEP  
  Empty param separator to parse cookies.
* PARSE_RAW  
  Do not interpret the parsed parameters.
* PARSE_DEFAULT  
  Interpret input as default formatted parameters.
* PARSE_URLENCODED  
  Urldecode single units of parameters, arguments and values.
* PARSE_DIMENSION  
  Parse sub dimensions indicated by square brackets.
* PARSE_QUERY  
  Parse URL querystring (same as http\Params::PARSE_URLENCODED|http\Params::PARSE_DIMENSION).
* PARSE_RFC5987
  Parse [RFC5987](http://tools.ietf.org/html/rfc5987) style encoded character set and language information embedded in HTTP header params.

## Properties:

* public array $params = NULL  
  The (parsed) parameters.
* public array $param_sep = http\Params::DEF_PARAM_SEP  
  The parameter separator(s).
* public array $arg_sep = http\Params::DEF_ARG_SEP  
  The argument separator(s).
* public array $val_sep = http\Params::DEF_VAL_SEP  
  The value separator(s).
* public int $flags = http\Params::PARSE_DEFAULT  
  The modus operandi of the parser. See http\Params::PARSE_* constants.
