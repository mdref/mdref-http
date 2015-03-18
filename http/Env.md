# class http\Env

The http\Env class provides static methods to manipulate and inspect the server's current request's HTTP environment.

## Changelog:

| Version | Change 
|---------|--------
| 2.4.0   | Split off pecl/[apfd](apfd) and pecl/[json_post](json_post)

## Request startup

In versions lower than 2.4.0, the http\Env module extends PHP's builtin POST data parser to be run also if the request method is not POST. Additionally it will handle application/json payloads if ext/json is available. Successfully parsed JSON will be put right into the $_POST array.

This functionality has been separated into two distict extensions, pecl/[apfd](apfd) and pecl/[json_post](json_post).

