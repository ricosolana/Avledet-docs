# Avledet

### `Avledet.version`
  > Returns `string`

  > Valheim version: `0.221.6`
  
### `Avledet.delta`
  > Returns `number` | **readonly**
  
  > The delta time for this frame
  
  > Equivalent to Unity `Time.deltaTime`
  
### `Avledet.id`
  > Returns `Int64` | **readonly**

  > The randomly generated server id.

  > Used primarily for determining ZDO
  ownership throughout gameplay.
  
### `Avledet.nanos`
  > Returns `Int64` | **readonly**

  > The time in nanoseconds
  
### `Avledet.time`
  > Returns `number` | **readonly**
  
  > The time in seconds
  
  > Equivalent to Unity `Time.time`

### `Avledet.time_multiplier`
  > Returns `number` | **readonly**
  
  > The rate at which the server time advances
  
  > I cant remember why I created this member, so use with caution

### `Avledet.world_time`
  > Returns `number`

  > The in-game time which determines the day/night cycle

### `Avledet.world_time_multiplier`
  > Returns `number`

  > The rate at which the worldTime advances. Setting to a value less than 1 will slow the rate 
  (might have weird client time-skip effects). Setting to a values greater than 1 will speed up the ingame time.
  
  > A simple use-case of this is the ingame-sleep time skip, which rapidly progresses the time until morning. See the 
  [Sleep mod](https://github.com/PeriodicSeizures/Avledet/blob/f89bdaf3f34826576ba9befb6a74a934ed4f3e88/data/mods/Sleep/Sleep.lua#L77)
  for more information regarding usages.

### `Avledet.world_ticks`
  > Returns `number` | **readonly**

  > Similar to world_time but in the scale of C# `DateTime.Ticks`

### `Avledet.day`
  > Returns `number`
  
  > The current day in the world as an integer

### `Avledet.time_of_day`
  > Returns `number`
  
  > The current relative time of day. 
  
  > An entire cycle is 1800, where a new day starts at 270.
    
  > | Time of day   | Start time  | End time     |
  > | :----------   | :---------- | :----------  |
  > | Morning       | 240         | 270          |
  > | Day           | 270         | 900          |
  > | Afternoon     | 900         | 1530         |
  > | Night         | 1530        | 240          |

  > Can set time of day, which will keep the current day, but switch around the time.
  
### `Avledet.is_morning`
  > Returns `boolean` | **readonly**
  
  > Whether the current time is morning

### `Avledet.is_day`
  > Returns `boolean` | **readonly**

  > Whether the current time is day

### `Avledet.is_afternoon`
  > Returns `boolean` | **readonly**
  
  > Whether the current time is the afternoon

### `Avledet.is_night`
  > Returns `boolean` | **readonly**
  
  > Whether the current time is night

### `Avledet.tomorrow_morning`
  > Returns `number` | **readonly**
  
  > The worldTime for the morning time pertaining to the current `day` + 1

### `Avledet.tomorrow`
> Returns `number` | **readonly**

  > The worldTime for the day time pertaining to the current `day` + 1

### `Avledet.tomorrow_afternoon`
> Returns `number` | **readonly**

  > The worldTime for the afternoon time pertaining to the current `day` + 1

### `Avledet.tomorrow_night`
> Returns `number` | **readonly**

  > The worldTime for the night time pertaining to the current `day` + 1

### `Avledet:subscribe(name, cb_func)`
  > Subscribe to a game event
  
  > The passed function will be called when the event fires
  
  >
  ```lua
  Avledet:subscribe('Enable', function()
    -- Will be dispatched only once when all plugins are loaded
  end)
  
  Avledet:subscribe('RouteInAll', 'ChatMessage', function(peer, targetZdoid, bytes)
    -- Will be dispatched whenever a peer calls RoutedRpc that is aimed towards all online peers
  end)
  ```
  
  > Available event handlers:
  
  > | Method            | Dispatched                                                                                                        | Passthrough                           | Example                                                                                       |
  > | :----------       | :------------------                                                                                               | :---------------:                     | :-------                                                                                      |
  > | `Enable`          | Server start                                                                                                      | :material-close:                      | `Avledet:subscribe('Enable', function() end)`                                                |
  > | `Disable`         | Server stop                                                                                                       | :material-close:                      | `Avledet:subscribe('Disable', function() end)`                                               |
  > | `Update`          | Server update loop                                                                                                | :material-close:                      | `Avledet:subscribe('Update', function() end)`                                                |
  > | `Periodic`        | Once every second                                                                                                 | :material-close:                      | `Avledet:subscribe('Periodic', function() end)`                                              |
  > | `Connect`         | Any peer connects                                                                                                 | `Peer`                                | `Avledet:subscribe('Connect', function(peer) end)`                                           |
  > | `Disconnect`      | Any peer disconnects                                                                                              | `Peer`                                | `Avledet:subscribe('Disconnect', function(peer) end)`                                        |
  > | `Join`            | Valid peer joins                                                                                                  | `Peer`                                | `Avledet:subscribe('Join', function(peer) end)`                                              |
  > | `Quit`            | Valid peer quits                                                                                                  | `Peer`                                | `Avledet:subscribe('Quit', function(peer) end)`                                              |
  > | `RpcIn`           | :material-monitor: :material-arrow-right: :material-server:                                                       | `Peer`, `...`                         | `Avledet:subscribe('RpcIn', 'PeerInfo', function(peer, bytes) end)`                          |
  > | `RpcOut`          | :material-server: :material-arrow-right: :material-monitor:                                                       | `Peer`, `...`                         | `Avledet:subscribe('RpcOut', 'PeerInfo', function(peer, bytes) end)`                         |
  > | `RouteIn`         | :material-monitor: :material-arrow-right: :material-server:                                                       | `Peer`, `ZDOID`, `...`                | `Avledet:subscribe('RouteIn', 'SetGlobalKey', function(peer, targetZdoid, key) end)`               |  
  > | `RouteInAll`      | :material-monitor: :material-arrow-right: :material-server: :material-arrow-right: :material-monitor-multiple:    | `Peer`, `ZDOID`, `...`                | `Avledet:subscribe('RouteInAll', 'DestroyZDO', function(peer, targetZdoid, bytes) end)`            |  
  > | `RouteOut`        | :material-server: :material-arrow-right: :material-monitor:                                                       | `Peer`, `ZDOID`, `...`                | `Avledet:subscribe('RouteOut', 'SleepStart', function(peer, targetZdoid) end)`                     |  
  > | `RouteOutAll`     | :material-server: :material-arrow-right: :material-monitor-multiple:                                              | `ZDOID`, `...`                        | `Avledet:subscribe('RouteOutAll', 'GlobalKeys', function(targetZdoid, keys) end)`                  |  
  > | `Routed`          | :material-monitor: :material-arrow-right: :material-server: :material-arrow-right: :material-monitor:             | `Peer-src` `Peer-dst`, `ZDOID`, `...` | `Avledet:subscribe('RouteOutAll', 'AddItem', function(srcpeer, dstpeer, targetZdoid, item) end)`   |  
  > | `Send`            | Server sends packet                                                                                               | `Socket`, `Bytes`                     | `Avledet:subscribe('Send', function(socket, bytes) end)`                                     |  
  > | `Recv`            | Server receives packet                                                                                            | `Socket`, `Bytes`                     | `Avledet:subscribe('Recv', function(socket, bytes) end)`                                     |  
  > | `POST`            | Event-modifier to run after the primary-event
  
  > Most of the events above are prefix methods like in Harmony. Similarly, there is a `POST` event that can be 
  called after the major event has taken place. This only applies to `Rpc<>` and `Route<>` events 
  (maybe also to some others not listed here).
  
  >
  ```lua
  -- Will be ran after the internal PeerInfo has taken place
  Avledet:subscribe('RpcIn', 'PeerInfo' 'POST', function(peer, bytes) end)
  ```
  
  > Handlers using `POST` cannot be cancelled unless otherwise stated (because what would be the point?).