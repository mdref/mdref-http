# void http\Client\Curl\User::init(callable $run)

Initialize the event loop.


## Params:

* callable $run as function(http\Client $c, resource $s = null, int $action = http\Client\Curl\User::POLL_NONE) : int  
  Internal callback returning the number of unfinished requests pending.


> ***NOTE***:  
> The callback should be run when a timeout occurs or a watched socket needs action.
