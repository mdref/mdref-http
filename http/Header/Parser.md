# class http\Header\Parser

The parser which is underlying http\Header and http\Message.

## Changelog:

| Version | Change 
|---------|--------
| 2.3.0   | Added http\Header\Parser API

## Constants:

### Parser flags:

* CLEANUP  
  Finish up parser at end of (incomplete) input.

### Parser states:

* STATE_FAILURE  
  Parse failure.
* STATE_START  
  Expecting HTTP info (request/response line) or headers.
* STATE_KEY  
  Expecting a key or already parsing a key.
* STATE_VALUE  
  Expecting a value or already parsing the value.
* STATE_VALUE_EX  
  At EOL of an header, checking whether a folded header line follows.
* STATE_HEADER_DONE  
  A header was completed.
* STATE_DONE  
  Finished parsing the headers.

> ***NOTE:***  
> Most of this states won't be returned to the user, because the parser immediately jumps to the next expected state.
