# Socket

The socket structure used throughout the game for Rpc-pings and Rpc invocations
    
This object is non-constructible.

## Instance Members

### `socket:close(flush: bool)`
  > Close the socket and/or linger a short time (3s) for unsent packets.

### `socket.address`
  > Returns `string` | **readonly**
  
  > The address of the remote socket.

### `socket.host`
  > Returns `string` | **readonly**
  
  > The unique hostname for the remote socket.
  
### `socket.send_queue_size`
  > Returns `number` | **readonly**
  
  > The total size of outgoing data in bytes. 

### `socket.status`
  > Returns `Status` | **readonly**
  
  > The connection status of the socket.

### `socket:send(packet: Bytes)`
  > Send the supplied packet to the remote host.

### `socket.ping`
  > Returns `number` | **readonly**
  
  > The one-way latency of the connection measured in whole milliseconds.

### `socket.quality`
  > Returns `local: number`, `remote: number` | **readonly**
  
  > The local and remote quality of the connection, measured as a fractional number in the range `[0.0, 1.0]`.

### `socket.outbound`
  > Returns `bool` | **readonly**
  
  > Whether we initiated this connection or the connection was accepted by us.