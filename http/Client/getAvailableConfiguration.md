# array http\Client::getAvailableConfiguration()

Get a list of available configuration options and their default values.

See f.e. the [configuration options for the Curl driver](http/Client/Curl#Configuration:).

## Params:

None.

## Returns:

* array, list of key/value pairs of available configuarion options and their default values.

## Throws:

* http\Exception\InvalidArgumentException

## Example:

	<?php
	
	$client = new http\Client("curl");
	var_dump($client->getAvailableConfiguration());
	
	?>

Yields:

	array(10) {
	  ["maxconnects"]=>
	  int(-1)
	  ["max_host_connections"]=>
	  int(0)
	  ["max_pipeline_length"]=>
	  int(5)
	  ["max_total_connections"]=>
	  int(0)
	  ["pipelining"]=>
	  bool(false)
	  ["chunk_length_penalty_size"]=>
	  int(0)
	  ["content_length_penalty_size"]=>
	  int(0)
	  ["pipelining_server_bl"]=>
	  NULL
	  ["pipelining_site_bl"]=>
	  NULL
	  ["use_eventloop"]=>
	  bool(false)
	}

