# (De)/compression

Compression and decompression utility classes.

## ZStd

### `ZStdCompressor.new()`
  > Returns `ZStdCompressor`

  > Create a new compressor using the default compression level of 3

### `ZStdCompressor.new(level: number)`
  > Returns `ZStdCompressor`

  > Create a new compressor using the provided level of compression

### `ZStdCompressor.new(dict: Bytes)`
  > Returns `ZStdCompressor`

  > Create a new compressor using a preassembled ZStd dictionary

### `zstdcompressor:compress(data: Bytes)`
  > Returns `Bytes`

  > Compresses and returns the given data or nil if an error occurred.

### `ZStdDecompressor.new()`
  > Returns `ZStdDecompressor`

  > Create a new decompressor

### `ZStdDecompressor.new(dict: Bytes)`
  > Returns `ZStdDecompressor`

  > Create a new decompressor using a preassembled ZStd dictionary

### `zstddecompressor:decompress(data: Bytes)`
  > Returns `Bytes`

  > Decompresses and returns the given data or nil if an error occurred.

## ZLib/gz

### `Deflator.gz()`
  > Returns `Deflator`

  > Creates a gunzip decompressor with best speed level.

### `Deflator.zlib()`
  > Returns `Deflator`

  > Creates a zlib decompressor with best speed level.

### `Deflator.raw()`
  > Returns `Deflator`

  > Creates a zlib decompressor with best speed level and no header.

### `deflator:compress(data: Bytes)`
  > Returns `Bytes`

  > Compresses and returns the given data or nil if an error occurred.

### `Inflator.gz()`
  > Returns `Inflator`

  > Creates a gunzip decompressor with best speed level.

### `Inflator.zlib()`
  > Returns `Inflator`

  > Creates a zlib decompressor with best speed level.

### `Inflator.auto()`
  > Returns `Inflator`

  > Creates a zlib decompressor with automagical decompression selection.

### `Inflator.raw()`
  > Returns `Inflator`

  > Creates a zlib decompressor with best speed level and no header.

### `inflator:decompress(data: Bytes)`
  > Returns `Bytes`

  > Decompresses and returns the given data or nil if an error occurred.