# class http\Client implements SplSubject, Countable

The HTTP client. See http\Client\Curl's [options](http/Client/Curl#Options:) which is the only driver currently supported.

## Constants:

* DEBUG_INFO
  Debug callback's $data contains human readable text.
* DEBUG_IN
  Debug callback's $data contains data received.
* DEBUG_OUT
  Debug callback's $data contains data sent.
* DEBUG_HEADER
  Debug callback's $data contains headers.
* DEBUG_BODY
  Debug callback's $data contains a body part.
* DEBUG_SSL
  Debug callback's $data contains SSL data.

## Properties:

* private SplObjectStorage $observers = NULL  
  Attached observers.
* protected array $options = NULL  
  Set options.
* protected http\Message $history = NULL  
  Request/response history.
* public bool $recordHistory = false  
  Whether to record history in http\Client::$history.
