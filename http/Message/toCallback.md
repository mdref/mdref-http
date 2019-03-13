# http\Message http\Message::toCallback(callable $callback)

Stream the message through a callback.

## Params:

* callable $callback  
  The callback of the form function(http\Message $from, string $data).

## Returns:

* http\Message, self.
