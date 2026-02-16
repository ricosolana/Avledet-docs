# Reference

Avledet utilizes Lua to take advantage of many of the available 
internal features. This is made possible with the sol Lua wrapper 
library. 

See [the code](https://github.com/ricosolana/Avledet/blob/fix-zdos/src/ModManager.cpp#L64)
for the actual implementation and stuff that might not
be fully included in this documentation

## Features

- Dynamic script reloading (triggered on scriptInfo.yml save)
- Scripts 100% sandboxed (same Lua state used, however globals are per-script)
- Work-in-progress Valheim mod rewrites

## Caveats

- Debug library and several os functions are disabled to preserve sandboxing
- Allowed functions:
  - assert, error, ipairs, next, pairs, pcall, print, select, tonumber, tostring, type, unpack, _VERSION, xpcall
  - coroutine.*, string.*, table.*, math.*
  - os.clock, os.date, os.difftime, os.time 

## sol2/lua Quirks

- C++ bound functions which return a reference `MyObject&` will actually be copied, unless std::ref is used.
    - such as in `NetManager.peers`, this list is effectively immutable, although its accessor function returns 
        a direct reference `std::vector<Peer::Ptr>&`.

- Although a single lua state is used for the servers scripting engine, plugins are isolated from
    other within independent lua environments.

- To achieve true lua script-script sandboxing, stls such as debug, os (partial), and other native libraries
    were disabled. 

## Documentation format

- Top-level `#` header (class name)
- Second-level `##` header (Class / Instance section)
- Third-level `###` header (Member name, func args)
    - Returns following a type
    - Description of the function and returned value (if any)

See the API [Random](usertypes/random.md) as an example for a tidy page layout.

The first half of a reference section will be statically callable class methods, like constructors and other global/instance independent mutators.

The second half will be instance members, which must be called on an instantiated or reference object.

### Danger zone

The previous project, Valhalla, used some awkward techniques for "performance",
at the sacrifice of safety. This revival project aims to make the lua api fully safe.

There are still some caveats