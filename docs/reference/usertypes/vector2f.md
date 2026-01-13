# Vector2f

A vector consisting of two floating point components

## Class Members

### `Vec2f.new()`
  > Returns `Vec2f`

  > Constructs a Vec2f equivalent to Vec2f.ZERO

### `Vec2f.new(x, y)`
  > Returns `Vec2f`

  > Constructs a Vec2f from x and y parameters

### `Vec2f.ZERO`
  > Returns `Vector2` | **readonly**
  
  > A zero vector (0, 0)

## Instance Members

### `vec2f.x`
  > Returns `number`

  > The x component of the vector

### `vec2f.y`
  > Returns `number`

  > The y component of the vector

### `vec2f.magnitude`
  > Result: `number` | **readonly**

  > The length of the vector
  
### `vec2f.sq_magnitude`
  > Result: `number` | **readonly**

  > The squared length of the vector

### `vec2f.normal`
  > Result: `Vec2f` | **readonly**
  
  > Returns the unit normal vector of this

### `vec2f:distance_to(other: Vec2f)`
  > Returns `number`

  > The distance another vector and this

### `vec2f:sq_distance_to(other: Vec2f)`
  > Result: `number`

  > The squared distance another vector and this

### `vec2f:__add()`
  > Returns `Vec2f`

  > Adds together two vectors
  
  > 
  ```lua
  local a = Vec2f.new(1, 5)
  local b = Vec2f.new(2, -1)
  
  -- (3, 4)
  local result = a + b
  ```

### `vec2f:__sub()`
  > Returns `Vec2f`

  > Subtracts two vectors
  
  > 
  ```lua
  local a = Vec2f.new(6, -1)
  local b = Vec2f.new(-3, -2)
  
  -- (9, 1)
  local result = a - b
  ```
  
### `vec2f:__mul()`
  > Returns `Vec2f`

  > Multiplies two vectors
  
  > 
  ```lua
  local a = Vec2f.new(1, 2)
  local b = Vec2f.new(4, 5)
  
  -- (4, 10)
  local result = a * b
  ```

### `vec2f:__div()`
  > Returns `Vec2f`

  > Divides two vectors

  > 
  ```lua
  local a = Vec2f.new(6, 4)
  local b = Vec2f.new(3, 2)
  
  -- (2, 2)
  local result = a / b
  ```