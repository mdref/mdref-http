# http\Client http\Client::configure(array $configuration)

Configure the client's low level options.

## Params:

 * array $configuration  
   Key/value pairs of low level options.  
   See f.e. the [configuration options for the Curl driver](http/Client/Curl#Configuration:).

## Returns:

* http\Client, self.

## Throws:

* http\Exception\InvalidArgumentException
* http\Exception\UnexpectedValueException

## Example:

	<?php
	
	$client = new http\Client("curl");
	$client->configure([
		"max_host_connections" => 8,
		"pipelining" => true,
	]);
	
	?>
