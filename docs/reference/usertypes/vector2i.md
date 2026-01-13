# Vec2i

A vector consisting of two integer components

## Class Members

### `Vec2i.new()`
  > Returns `Vec2i`

  > Constructs a Vec2i equivalent to Vec2i.ZERO

### `Vec2i.new(x, y, z)`
  > Returns `Vec2i`

  > Constructs a Vec2i from x and y parameters

### `Vec2i.ZERO`
  > Returns `Vec2i` | **readonly**
  
  > A zero vector (0, 0)

## Instance Members

### `vec2i.x`
  > Returns `number`

  > The x component of the vector

### `vec2i.y`
  > Returns `number`

  > The y component of the vector

### `vec2i.magnitude`
  > Result: `number` | **readonly**

  > The length of the vector
  
### `vec2i.magnitude`
  > Result: `number` | **readonly**

  > The squared length of the vector

### `vec2i.normal`
  > Result: `Vec2i` | **readonly**
  
  > Returns the unit normal vector of this

### `vec2i:distance_to(other: Vec2i)`
  > Returns `number`

  > The distance another vector and this

### `vec2i:sq_distance_to(other: Vec2i)`
  > Result: `number`

  > The squared distance another vector and this

### `vec2i:__add()`
  > Returns `Vec2i`

  > Adds together two vectors
  
  > 
  ```lua
  local a = Vec2i.new(1, 5)
  local b = Vec2i.new(2, -1)
  
  -- (3, 4)
  local result = a + b
  ```

### `vec2i:__sub()`
  > Returns `Vec2i`

  > Subtracts two vectors
  
  > 
  ```lua
  local a = Vec2i.new(6, -1)
  local b = Vec2i.new(-3, -2)
  
  -- (9, 1)
  local result = a - b
  ```
  
### `vec2i:__mul()`
  > Returns `Vec2i`

  > Multiplies two vectors
  
  > 
  ```lua
  local a = Vec2i.new(1, 2)
  local b = Vec2i.new(4, 5)
  
  -- (4, 10)
  local result = a * b
  ```

### `vec2i:__div()`
  > Returns `Vec2i`

  > Divides two vectors

  > 
  ```lua
  local a = Vec2i.new(6, 4)
  local b = Vec2i.new(3, 2)
  
  -- (2, 2)
  local result = a / b
  ```