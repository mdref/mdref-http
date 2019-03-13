# static string http\Encoding\Stream\Enbrotli::encode(string $data[, int $flags = 0])

Encode data with brotli encoding.

## Params:

* string $data  
  The data to compress.
* Optional int $flags = 0  
  Any compression tuning flags. See http\Encoding\Stream\Enbrotli and http\Encoding\Stream constants.

## Returns:

* string, the compressed data.

## Warnings:

* If $data cannot be encoded.
