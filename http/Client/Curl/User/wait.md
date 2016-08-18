# void http\Client\Curl\User::wait([int $timeout_ms = null])

Wait/poll/select (block the loop) until events fire.

> ***NOTE:***
> This method is called by http\Client::wait(), so it does not need to have an actual implementation if http\Client::wait() is never called.

## Params:

* Optional int $timeout_ms = null
  Block for at most this milliseconds.
