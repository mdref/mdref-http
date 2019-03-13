# static string http\Env::negotiateCharset(array $supported[, array &$result])

Negotiate the client's preferred character set.

> ***NOTE:***  
> The first element of $supported character sets serves as a default if no character set matches.

## Params:

* array $supported  
  List of supported content character sets.
* Optional array &$result  
  Out parameter recording negotiation results.
  
## Returns:

* NULL, if negotiation fails.
* string, the negotiated character set.
