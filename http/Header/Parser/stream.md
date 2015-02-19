# int http\Header\Parser::stream(resource $stream, int $flags, array &$headers)

Parse a stream.

## Params:

* stream $resource  
  The header stream to parse from.
* int $flags  
  Any combination of [parser flags](http/Header/Parser#Parser.flags:).
* array &$headers  
  The headers parsed.

## Returns:

* int, http\Header\Parser::STATE_* constant.

## Throws:

* http\Exception\InvalidArgumentException
* http\Exception\UnexpectedValueException
