# Int64

Wrapper type for 64-bit integers because of Luas inability to support them

## Class Members

### `Int64.new(...)`
  > Returns `Int64`
  
  > `Int64.new()`, `Int64.new(number)`, `Int64.new(lower, upper)`,
    `Int64.new(hexstring)`
  
## Instance Members

### `int64:tonumber()`
  > Returns `number`
  
  > Directly returns the underlying value as a Lua number
  
  > This should only be called assuming the integral value 
    can be represented by a double (up to numbers ~2^35)

## Metamethods / operators
    
### `int64:__add()`
  > Returns `Int64`
  
### `int64:__sub()`
  > Returns `Int64`
  
### `int64:__mul()`
  > Returns `Int64`
  
### `int64:__div()`
  > Returns `Int64`
  
### `int64:__divi()`
  > Returns `Int64`
  
### `int64:__unm()`
  > Returns `Int64`
  
  > Unary minus. Negation of the object.
  
  > `-int64`
  
### `int64:__eq()`
  > Returns `Int64`
  
### `int64:__lt()`
  > Returns `Int64`
  
### `int64:__leq()`
  > Returns `Int64`
  