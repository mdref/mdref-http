# http\Client http\Client::enablePipelining([bool $enable = true])

Enable sending pipelined requests to the same host if the driver supports it.

> ***NOTE:***  
> This method has been deprecated in 2.3.0, please use http\Client::configure() instead.

## Params:

* Optional bool $enable = true  
  Whether to enable pipelining.

## Returns:

* http\Client, self.

## Throws:

* http\Exception\InvalidArgumentException
* http\Exception\UnexpectedValueException

## Changelog:

Version | Change
--------|-------
2.3.0   | This method has been deprecated.
