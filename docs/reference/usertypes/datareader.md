# Reader

A deserializing utility. Is essentially a wrapper around a `Bytes` object

Note: Any of the Read...() methods below will throw if the length is exceeded. 
Objects which start with a 32-bit signed size will throw if the size is negative.

## Class Members

### `Reader.new(bytes)`
  > Returns `Reader`

  > Constructs a Reader using a specified byte buffer
  
## Instance Members

### `reader.pos`
  > Returns `number`
  
  > The current position of the reader
  
  > Will throw if set position is invalid
  
### `reader:seek(advance: number)`  
  > Seek ahead or backwards (if negative) in the stream
  
  > Will throw if final position is invalid.

### `reader:read_bool()`
  > Returns `boolean`
  
  > Reads a boolean from the stream and advances the position by `1`
  
### `reader:read_string()`
  > Returns `string`
  
  > Reads a string from the stream and advances the position by `4 + <size>`

### `reader:read_strings()`
  > Returns `container<string>`
  
  > Reads several strings from the stream and advances the position by `4 + <count>`
  
### `reader:read_bytes()`
  > Returns `Bytes`
  
  > Reads a byte buffer from the stream and advances the position by `4 + <size>`
  
### `reader:read_zdoid()`
  > Returns `ZDOID`
  
  > Reads a ZDOID from the stream and advances the position by `12`
  
### `reader:read_vec3f()`
  > Returns `Vector3`
  
  > Reads a Vector3 from the stream and advances the position by `12`
  
### `reader:read_vec2i()`
  > Returns `Vector2i`
  
  > Reads a Vector2i from the stream and advances the position by `8`
  
### `reader:read_quat()`
  > Returns `Quaternion`
  
  > Reads a Quaternion from the stream and advances the position by `16`
  
### ~~`reader:ReadProfile()`~~
  > Returns `UserProfile`
  
  > Reads a UserProfile from the stream and advances the position by `16`
  
### `reader:read_s8()`
  > Returns `number`
  
  > Reads an 8-bit signed integer from the stream and advances the position by `1`
  
### `reader:read_s16()`
  > Returns `number`
  
  > Reads a 16-bit signed integer from the stream and advances the position by `2`
  
### `reader:read_s32()`
  > Returns `number`
  
  > Reads a 32-bit signed integer from the stream and advances the position by `4`
  
### `reader:read_s64()`
  > Returns `Int64`
  
  > Reads a 64-bit signed integer from the stream and advances the position by `8`
  
### `reader:read_u8()`
  > Returns `number`
  
  > Reads an 8-bit unsigned integer from the stream and advances the position by `1`
  
### `reader:read_u16()`
  > Returns `number`
  
  > Reads an 16-bit unsigned integer from the stream and advances the position by `2`
  
### `reader:read_u32()`
  > Returns `number`
  
  > Reads an 32-bit unsigned integer from the stream and advances the position by `4`
  
### `reader:read_u64()`
  > Returns `UInt64`
  
  > Reads an 64-bit unsigned integer from the stream and advances the position by `8`
  
### `reader:read_float()`
  > Returns `number`
  
  > Reads a 32-bit floating point number from the stream and advances the position by `4`
  
### `reader:read_double()`
  > Returns `number`
  
  > Reads a 64-bit floating point number from the stream and advances the position by `8`
  
### `reader:read_char16()`
  > Returns `number`
  
  > Reads a variable length UTF8 character from the stream and advances the position by a max of `3`
  