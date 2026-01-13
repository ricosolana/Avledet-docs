# Peer

## Instance Members

### `peer.marker`
  > Returns `boolean`
  
### `peer.admin`
  > Returns `boolean`

### `peer.character_id`
  > Returns `ZDOID` | **readonly**
  
### `peer.name`
  > Returns `string` | **readonly**
  
### `peer.pos` 
  > Returns `Vector3`
  
  > The occasionally updated position of the Peer
  
### ~~`peer.uuid`~~
  > Returns `Int64` | **readonly**
  
### `peer.socket`
  > Returns `Socket` | **readonly**
  
### `peer.zdo`
  > Returns `ZDO` | **readonly**

  > Returns `nil` if player hasnt completed login, or during death.
  
### `peer:kick()`

### `peer:chat_message(message: string)`
  > Send a basic chat message to the Peer
  
### `peer:console_message(message: string)`
  > Send a console message to the Peer
  
### `peer:corner_message(message: string)`
  > Send a top-left screen message to the Peer
  
### `peer:center_message(message: string)`
  > Send a top screen message to the Peer
  
### `peer:teleport(pos: Vec3f, rot: Quaternion, animate: boolean)`
  > Slowly teleports the player to a location.
  
  > If `animate` is set, teleports the player with a portal overlay

### `peer:teleport(pos: Vec3f, rot: Quaternion)`
  > Slowly teleports the player to a location
  
  > Calls peer:Teleport(...) with `animate` set to false
  
### `peer:disconnect()`
  > Disconnect the peer from the server
  
  > The connection will linger for a while, but the Peer will be disposed
  of during the next frame
  
### `peer:invoke_self(hash, dataReader)`
  > Emulates an invoke call normally performed by the remote Peer
  
  > Expects a numeric hash for the method name
  
### `peer:InvokeSelf(name, dataReader&)

### `peer:Register(methodSig, rpc)`
  > Registers an Rpc function
  
  > The register Rpc handler can return an optional boolean determining
  whether the handler should unregister once finished calling.
  
  > 
  ```lua
  local SIG_CompressHandshake = MethodSig.new("CompressHandshake", Type.BOOL)
  
  -- in an event which provides a peer or equivalent...
  peer:Register(SIG_CompressHandshake, function(peer, enabled)
      -- called every time the remote peer invokes 'CompressHandshake'
      
      -- 'enabled' will be passed as a boolean
      
      -- 'false' to dispose this rpc handler after being called
      return false
  end)  
  ```

### `peer:Invoke(methodSig, ...)`
  > Invokes a method remotely for reception by the remote peer.
  
  > 
  ```lua
  local SIG_CompressHandshake = MethodSig.new("CompressHandshake", Type.BOOL)
  
  -- in an event which provides a peer or equivalent...
  
  -- in the Peer:Register example above, 'true' would be passed to the handler
  peer:Invoke(SIG_CompressHandshake, true)
  ```
  
### `peer:RouteView(targetZdoid, methodSig, ...)`
  > Invoke a RoutedRpc function remotely.
  
  > This is the RoutedRpc call bound to a specific Peer NetView
  
  > The usage of this is equivalent to `peer:Invoke`
  
### `peer:Route(methodSig, ...)`
  > Invoke a RoutedRpc function remotely.
  
