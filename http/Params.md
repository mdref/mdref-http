# class http\Params implements ArrayAccess

Parse, interpret and compose HTTP (header) parameters.

## Changelog:

Version | Change
--------|-------
2.1.0   | Added [RFC5987](http://tools.ietf.org/html/rfc5987) support
2.5.0   | Added [RFC5988](http://tools.ietf.org/html/rfc5987) support

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

## Web Linking Example:

	$link = <<<EOF
	Link: </TheBook/chapter2>;
			 rel="previous"; title*=UTF-8'de'letztes%20Kapitel,
			 </TheBook/chapter4>;
			 rel="next"; title*=UTF-8'de'n%c3%a4chstes%20Kapitel
	EOF;
	
	$p = current(http\Header::parse($link, "http\\Header"))->getParams(
		http\Params::DEF_PARAM_SEP,
		http\Params::DEF_ARG_SEP,
		http\Params::DEF_VAL_SEP,
		http\Params::PARSE_RFC5988 | http\Params::PARSE_ESCAPED
	);
	
	var_dump($p->params);
	var_dump((string)$p);

Yields:

	array(2) {
	  ["/TheBook/chapter2"]=>
	  array(2) {
		["value"]=>
		bool(true)
		["arguments"]=>
		array(2) {
		  ["rel"]=>
		  string(8) "previous"
		  ["*rfc5987*"]=>
		  array(1) {
			["title"]=>
			array(1) {
			  ["de"]=>
			  string(15) "letztes Kapitel"
			}
		  }
		}
	  }
	  ["/TheBook/chapter4"]=>
	  array(2) {
		["value"]=>
		bool(true)
		["arguments"]=>
		array(2) {
		  ["rel"]=>
		  string(4) "next"
		  ["*rfc5987*"]=>
		  array(1) {
			["title"]=>
			array(1) {
			  ["de"]=>
			  string(17) "nächstes Kapitel"
			}
		  }
		}
	  }
	}
	string(139) "</TheBook/chapter2>;rel="previous";title*=utf-8'de'letztes%20Kapitel,</TheBook/chapter4>;rel="next";title*=utf-8'de'n%C3%A4chstes%20Kapitel"

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
* PARSE_RFC5988
  Parse [RFC5988](http://tools.ietf.org/html/rfc5988) (Web Linking) tags of Link headers.

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
