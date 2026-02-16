# Avledet 

Dedicated server for Valheim written in C++

### Overview

Avledet is an implementation of the Valheim dedicated server written in C++.
Avledet not only includes, but expands upon the vanilla Valheim server
config. Some of the settings involve packet rates, world-gen, creature spawning 
and more. 

### World

World loading is fully supported with an optional legacy mode
to support loading very old worlds. Saving is also fully functional with 
customizable save times and compressed rolling backups.

### Lua API

Avledet includes a feature-rich Lua API to manipulate the inner-workings 
of the server. See the [API reference](reference/index.md) for more details and 
documentation.

Several already-created mods are included with Valhalla to serve as 
examples and demonstrations of what is possible with the API.

Several of these implement core functionality of Valheim but can be
removed. Note that this might affect sleeping and/or portals.

An implementation of the BetterNetworking mod exists to support
compatible mod. It fully supports
compression and the other mod-specific settings (like send rates) 
are already built into the server config.