# Enums

Several labeled constants are used throughout Valhalla, and they are listed here
for easy reference.

They can be accessed by the name of the enum table and the enum itself:

  > `TimeOfDay.DAY`
  
  > `Flag.CHAIR`
  
### `Type`
  > | Type        | Alias           | Description
  > | :---------- | :-------------- | :----------
  > | BOOL        |                 | 1 byte boolean
  > | STRING      | str             | var-length encoded string
  > | STRINGS     | strs            | array of string
  > | BYTES       |                 | array of bytes
  > | ZDOID       | zid             |  
  > | VECTOR3     | vec3f           | 3 floats
  > | VECTOR2i    | vec2i           | 2 signed ints
  > | QUATERNION  | quat            | 4 floats
  > | INT8        | i8              |
  > | INT16       | SHORT, i16      |
  > | INT32       | INT, i32, HASH  | 
  > | INT64       | LONG, i64       |
  > | UINT8       | BYTE, u8        |
  > | UINT16      | USHORT, u16     |
  > | UINT32      | UINT, u32       |
  > | UINT64      | ULONG, u64      |
  > | FLOAT       | f32             |
  > | DOUBLE      | f64             |
  > | CHAR16      | utf             | utf8 encoded character (1-3 bytes)
  
### `TimeOfDay`
  > | TimeOfDay   | Value      
  > | :---------- | :----------
  > | MORNING     | 240        
  > | DAY         | 270        
  > | AFTERNOON   | 900        
  > | NIGHT       | 1530       
  
### `ChatMsgType`
  > | ChatMsgType
  > | :----------
  > | WHISPER    
  > | NORMAL        
  > | SHOUT  
  > | PING

### `Flag`
  > Prefab flags which are to be masked together as bitmasks

  > | Flag          | Description
  > | :----------   | :----------
  > | NONE          | 
  > | SCALE         | Send initial scale
  > | DISTANT       | Is an object visible from far away
  > | PERSISTENT    | Is a transient server object (saveable to disk)
  > | TYPE1         | bit 1
  > | TYPE2         | bit 2
  > | PIECE         | Is a player placed object
  > | BED           | Is a bed
  > | DOOR          | Is a door
  > | CHAIR         | Is a chair
  > | SHIP          | Is a sailable ship
  > | FISH          | Is a swimming fish
  > | PLANT         | Is a player-plantable crop
  > | ARMOR_STAND   | Is an armorstand that hold items
  > | PROJECTILE    | Is a shot projectile
  > | ITEM_DROP     | Is a dropped ground item
  > | PICKABLE      | Is a player-interactible object
  > | PICKABLE_ITEM | Is a one-time pickable loot item
  > | CONTAINER     | Is an inventory, most associated with chests
  > | COOKING_STATION   | Is a cooking station
  > | CRAFTING_STATION  | Is a crafting station
  > | SMELTER           | Is an material refining station
  > | FIREPLACE         | Is a torch or other campfire type
  > | WEAR_N_TEAR       | Is a supportable structure with strength
  > | BREAKABLE         | Is a destructible object capable of taking damage
  > | ITEM_STAND        | Is a utility component that holds items in physical space
  > | ANIMAL_AI         | Is a passive creature
  > | MONSTER_AI        | Is a neutral or hostile creature
  > | TAMEABLE          | Is a tameable creature
  > | PROCREATION       | Is a breedable creature
  > | MINE_ROCK_5       | Is a pickaxe-mineable object
  > | TREE_BASE         | Is an upright tree
  > | TREE_LOG          | Is a downed rolling tree log
  > | DUNGEON           | Is a dungeon object
  > | TERRAIN_MODIFIER  | Is a placed landscaping edit
  > | CREATURE_SPAWNER  | Is a spawning creature nest