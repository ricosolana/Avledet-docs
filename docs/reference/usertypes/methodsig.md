# MethodSig

A structure which represents a handle to an arbitrary method.

Used for custom RPC or RoutedRpc registrations.

### `MethodSig.new(name, ...)`
  > Returns `MethodSig`
  
  > Constructs a `MethodSig` object expecting a `string` for name 
  and variadic arguments `...` for the function parameters.
  
  > 
  ```lua
  local SIG_SleepStart = MethodSig.new('SleepStart')
  
  local SIG_Discover = MethodSig.new("DiscoverClosestLocation", 
      Type.str, Type.vec3f, Type.str, Type.i32, Type.BOOL
  )
  
  -- https://github.com/M4cs/Valheim-Server-RPC-Guide#our-custom-handlers
  local SIG_RequestServerAnnouncement = MethodSig.new('RequestServerAnnouncement', Type.BYTES)
  ```