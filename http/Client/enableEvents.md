# http\Client http\Client::enableEvents([bool $enable = true])

Enable usage of an event library like libevent, which might improve performance with big socket sets.

> ***NOTE:***  
> This method has been deprecated in 2.3.0, please use http\Client::configure() instead.

## Params:

* Optional bool $enable = true  
  Whether to enable libevent usage.

## Returns:

* http\Client, self.

## Throws:

* http\Exception\InvalidArgumentException
* http\Exception\UnexpectedValueException

## Changelog:

Version | Change
--------|-------
2.3.0   | This method has been deprecated.
