# interface http\Client\Curl\User

Interface to an user event loop implementation for http\Client::configure()'s $use_eventloop option.

> ***NOTE:***
> This interface was added in v2.6.0, resp. v3.1.0.

## Constants:

* POLL_NONE
  No action.
* POLL_IN
  Poll for read readiness.
* POLL_OUT
  Poll for write readiness.
* POLL_INOUT
  Poll for read/write readiness.
* POLL_REMOVE
  Stop polling for activity on this descriptor.
