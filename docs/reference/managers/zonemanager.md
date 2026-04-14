# ZoneManager

Manager class for all things related to world generation.

## Class Members

nothing here

## Instance Members

### `ZoneManager:populate_zone(zone: Vec2s)`
  > Forcibly generates a zone in world
  
  > Will spawn all new features and vegetation with no deletion

### `ZoneManager:find_nearest_feature(name, pos: Vec2s)`
  > Returns `FeatureInstance` or `nil`
  
  > Finds the Feature nearest to position with the given name 
  
### `ZoneManager:to_zone_pos(pos: Vec3f)`
  > Returns `Vec2s`
  
  > Converts from world coordinates to zone coordinates
  
### `ZoneManager:to_world_pos(zone: Vec2s)`
  > Returns `Vec3f`
  
  > Converts from zone coordinates to world coordinates
  
### `ZoneManager.global_keys`
  > Returns `string container` | **readonly**
  
  > The currently active global keys. 
  See [Global keys](https://valheim.fandom.com/wiki/Global_Keys)
  for more information.