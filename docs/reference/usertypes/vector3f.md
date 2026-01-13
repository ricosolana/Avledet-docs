# Vec3f

A vector consisting of three floating point components

### `Vec3f.new()`
  > Returns `Vec3f`

  > Constructs a Vec3f equivalent to Vec3f.ZERO

### `Vec3f.new(x, y, z)`
  > Returns `Vec3f`

  > Constructs a Vec3f from x, y, and z parameters

### `Vec3f.ZERO`
  > Returns `Vec3f`
  
  > A zero vector (0, 0, 0)

### `vec3f.x`
  > Returns `number`

  > The x component of the vector

### `vec3f.y`
  > Returns `number`

  > The y component of the vector

### `vec3f.z`
  > Returns `number`

  > The z component of the vector
  
### `vec3f.magnitude`
  > Returns `number` | **readonly**

  > The length of the vector
  
### `vec3f.sq_magnitude`
  > Returns `number` | **readonly**

  > The squared length of the vector

### `vec3f.normal`
  > Result: `Vec3f` | **readonly**
  
  > Returns the unit normal vector of this

### `vec3f:distance_to(other: Vec3f)`
  > Returns `number`

  > The distance another vector and this

### `vec3f:sq_distance_to(other: Vec3f)`
  > Returns `number`

  > The squared distance another vector and this

### `vec3f:__add()`
  > Returns `Vec3f`

  > Adds together two vectors
  
  > 
  ```lua
  local a = Vec3f.new(1, 0.5, 1)
  local b = Vec3f.new(2, -1, -2)
  
  -- (3, -0.5, -1)
  local result = a + b
  ```

### `vec3f:__sub()`
  > Returns `Vec3f`

  > Subtracts two vectors

  > 
  ```lua
  local a = Vec3f.new(6, -2.3, -4)
  local b = Vec3f.new(-3, -2, 2)
  
  -- (9, -0.3, -6)
  local result = a - b
  ```

### `vec3f:__mul()`
  > Returns `Vec3f`

  > Multiplies two vectors
  
  > 
  ```lua
  local a = Vec3f.new(1, 2, 3)
  local b = Vec3f.new(4, 5, 6)
  
  -- (4, 10, 18)
  local result = a * b
  ```

### `vec3f:__div()`
  > Returns `Vec3f`

  > Divides two vectors

  > 
  ```lua
  local a = Vec3f.new(6, 4, 10)
  local b = Vec3f.new(3, 2, 2)
  
  -- (2, 2, 5)
  local result = a / b
  ```
