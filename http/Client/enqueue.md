# http\Client http\Client::enqueue(http\Client\Request $request[, callable $cb])

Add another http\Client\Request to the request queue.
If the optional callback $cb returns true, the request will be automatically dequeued.

> ***Note:***
> The http\Client\Response object resulting from the request is always stored in an internal storage, __even__ when callback is used, because of that, the memory may grow up significantly if you send many many requests using the same http\Client instance... In that case, to keep memory as low as possible, it is advised to call http\Client::getResponse() in the callback or to call http\Client::reset() after each http\Client::send() to free some ressources.

See http\Client::dequeue() and http\Client::send().


## Params:

* http\Client\Request $request  
  The request to enqueue.
* Optional callable $cb  
  A callback to automatically call when the request has finished.

## Returns:

* http\Client, self.

## Throws:

* http\Exception\InvalidArgumentException
* http\Exception\BadMethodCallException
* http\Exception\RuntimeException

## Example:

    (new http\Client)->enqueue(new http\Client\Request("GET", "http://php.net"), 
        function(http\Client\Response $res) {
            printf("%s returned %d\n", $res->getTransferInfo("effective_url"), $res->getResponseCode());
            return true; // dequeue
    })->send();

Yields:

    http://php.net/ returned 200
