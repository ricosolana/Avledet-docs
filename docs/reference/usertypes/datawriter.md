# Writer

A fast utility class for serializing objects.

## Class Members

### `Writer.new(bytes)`
  > Returns `Writer`

  > Constructs a writer using a specified buffer

  > This object must not exist beyond the scope of its
  underlying vector. Doing so will cause segfaults.
  
## Instance Members
  
### `writer.pos`
  > Returns `number`
  
  > The current position of the writer
  
  > Will throw if set position is invalid

### `reader:seek(advance: number)`  
  > Seek ahead or backwards (if negative) in the stream
  
  > Will throw if final position is invalid.

### `reader:write_bool(bool)`
  > Writes a `bool` to the stream
  
### `reader:write_string(string)`
  > Writes a `string` to the stream

### `reader:write_strings(strings)`  
  > Writes a `container<string>` to the stream

### `reader:write_bytes(bytes)`  
  > Writes a `Bytes` object to the stream

### `reader:write_zdoid(zdoid)`  
  > Writes a `ZDOID` to the stream

### `reader:write_vec3f(vec3f)`  
  > Writes a `Vec3f` to the stream

### `reader:write_vec2i(vec2i)`  
  > Writes a `Vec2i` to the stream

### `reader:write_quat(quat)`  
  > Writes a `Quaternion` to the stream

### `writer:write_i8(value)`
  > Writes a `number`, `Int64`, or `UInt64` as a signed 8 bit integer
  
### `writer:write_i16(value)`
  > Writes a `number`, `Int64`, or `UInt64`as a signed 16 bit integer
  
### `writer:write_i32(value)`
  > Writes a `number`, `Int64`, or `UInt64`as a signed 32 bit integer

### `writer:write_i64(value)`
  > Writes a `Int64` or `UInt64` as a signed 64 bit integer
  
### `writer:write_u8(value)`
  > Writes a `number`, `Int64`, or `UInt64`as an unsigned 8 bit integer
  
### `writer:write_u16(value)`
  > Writes a `number`, `Int64`, or `UInt64` as an unsigned 16 bit integer
  
### `writer:write_u32(value)`
  > Writes a `number`, `Int64`, or `UInt64` as an unsigned 32 bit integer
  
### `writer:write_u64(value)`
  > Writes a `Int64` or `UInt64` as an unsigned 64 bit integer
  
### `writer:write_float(value)`
  > Writes a `number` as an 32 bit floating point number
  
### `writer:write_double(value)`
  > Writes a `number` as an 64 bit floating point number
  
### `writer:write_char16(value)`
  > Writes a `number` as a variable length UTF8 character
  
  > Must fit within a c++ `char16_t`
  
  > Up to `3` bytes will be written

### `writer:write(obj: Any)`
  > An overload for writing an object to the underlying buffer
  
  > Accepts: `boolean`, `string`, `Bytes`, `ZDOID`, `Vec3f`, 
  ` Vec2i`, `Quaternion`, `Int64`, `UInt64`
  >> 
  ```lua
  writer:write(
    ZDOID.new(1, 2))
  ```

  > Accepts: `type: Type`, `obj: Any`
  >> 
  ```lua
  writer:write(Type.HASH, -- *Type.HASH is an alias for Type.s32
    VUtils.String.GetStableHashCode('secret')) -- HashCode returns a number
  ```

  > Accepts: `types: sequence<Type...>, objs: ...`
  >> 
  ```lua
  writer:write({Type.HASH, Type.float}, 
    VUtils.String.GetStableHashCode('secret2'), 
    3.14159)
  ```