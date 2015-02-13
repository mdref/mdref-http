# class http\Client implements SplSubject, Countable

The HTTP client. See http\Client\Curl's [options](http/Client/Curl#Options:) which is the only driver currently supported.

## Changelog:

Version | Change
--------|-------
2.3.0   | Deprecated methods:<br>http\Client::enablePipelining() and <br>http\Client::enableEvents().<br>Added Methods:<br>http\Client::configure(),<br>http\Client::getAvailableConfiguration() and<br>http\Client::getAvailableOptions().

## Examples:

### Sending a simple GET request:

    <?php

    $request = new http\Client\Request("GET",
        "http://localhost",
        ["User-Agent"=>"My Client/0.1"]
    );
    $request->setOptions(["timeout"=>1]);

    $client = new http\Client;
    $client->enqueue($request)->send();

    // pop the last retrieved response
    $response = $client->getResponse();
    printf("%s returned '%s' (%d)\n",
        $response->getTransferInfo("effective_url"),
        $response->getInfo(),
        $response->getResponseCode()
    );
    ?>

#### Yields:

    http://localhost/ returned 'HTTP/1.1 200 OK' (200)


### Submitting a standard form:

    <?php

    $request = new http\Client\Request("POST",
        "http://localhost/post.php",
        ["Content-Type" => "application/x-www-form-urlencoded"]
    );
    $request->getBody()->append(new http\QueryString([
        "user" => "mike",
        "name" => "Michael Wallner"
    ]));

    $client = new http\Client;
    $client->setOptions(["ssl" => [
		"version" => http\Client\Curl\SSL_VERSION_TLSv1
	]]);
	$client->enqueue($request)->send();

	// ask for the response for this specific request
	$response = $client->getResponse($request);
	printf("-> %s\n", $response->getInfo());

	?>

#### Yields:

    -> HTTP/1.1 200 OK


### Submitting a multipart form:

    <?php

    $request = new http\Client\Request("POST",
        "http://localhost/post.php"
    );

    // http\Message\Body::addForm() will automatically add
    // Content-Type: multipart/form-data to the request headers
    $request->getBody()->addForm([
        "user" => "mike",
        "name" => "Michael Wallner"
    ], [
        [
            "name" => "image",
            "type" => "image/jpeg",
            "file" => "image.jpg"
        ]
    ]);

    $client = new http\Client;
    $client->setOptions(["ssl" => [
        "version" => http\Client\Curl\SSL_VERSION_TLSv1
    ]]);
    $client->enqueue($request)->send();

    // ask for the response for this specific request
    $response = $client->getResponse($request);
    printf("-> %.2F kB\n @ %.2F Mbit",
        .001 * $response->getTransferInfo("size_upload"),
        .0000008 * $response->getTransferInfo("speed_upload")
    );
    ?>

#### Yields:

    -> 15.98 kB @ 6.77 Mbit


## Properties:

* private SplObjectStorage $observers = NULL  
  Attached observers.
* protected array $options = NULL  
  Set options.
* protected http\Message $history = NULL  
  Request/response history.
* public bool $recordHistory = false  
  Whether to record history in http\Client::$history.
