# class http\Params implements ArrayAccess

Parse, interpret and compose HTTP (header) parameters.

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
* PARSE_ESCAPED  
  Parse backslash escaped (quoted) strings.
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
