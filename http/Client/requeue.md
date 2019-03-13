# http\Client http\Client::requeue(http\Client\Request $request[, callable $cb])

Requeue an http\Client\Request.

The difference simply is, that this method, in contrast to http\Client::enqueue(), does not throw an http\Exception when the request to queue is already enqueued and dequeues it automatically prior enqueueing it again.


## Params:

* http\Client\Request $request  
  The request to queue.
* Optional callable $cb as function(\http\Response $response) : ?bool  
  A callback to automatically call when the request has finished.
 
## Returns:

* http\Client, self.

## Throws:

* http\Exception\InvalidArgumentException
* http\Exception\RuntimeException
