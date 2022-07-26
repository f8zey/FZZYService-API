## FZZYService's API

### `.NewService(INSTANCE)`
#### Used when requiring the Service, the Service will not work unless this line is present.
```lua
local ServerStorage = game:GetService("ServerStorage")
local FZZYServiceFolder = ServerStorage:WaitForChild("FZZYServiceFolder")

local FZZYService = require(FZZYServiceFolder.FZZYServiceModule).NewService(script)
```
### `:Stop()`
#### Instantly stops the Service, functions will not work until it's turned on again.
```lua
FZZYService:Stop()
```
### `:Start()`
#### Turns on the Service, this line cannot be run if the Service is already turned on.
```lua
FZZYService:Start()
```
### `:getPlayerCount()`
#### Returns a number variable of how many players are in the current server.
```lua
print(FZZYService:getPlayerCount())
```
### `:getJobId()`
#### Returns a string with the current server's JobId.
```lua
local JobId = FZZYService:getJobId()
print(JobId)
```
### `:createKey()`
#### Creates a GUID Data-Type key and adds it to a list of running keys, it returns the GUID key on creation.
```lua
local NewKey = FZZYService:createKey()
print(NewKey)
```
### `:removeKey(GUID_KEY)`
#### Deletes a GUID Data-Type key from a list of running keys (array table).
```lua
FZZYService:removeKey(OLD_KEY)
```
### `:findKey(GUID_KEY)`
#### Returns the found key from the list of running keys (array table), will return `nil` if no key is found.
```lua
local Key = FZZYService:findKey(OLD_KEY)
if Key ~= nil then
  print("The key is still alive!")
end
```
### `:getPlayer(PLAYER_INSTANCE)`
#### Returns the player from the PlayerService.
```lua
local Player = FZZYService:getPlayer("PLAYER")
print(Player.." is in the server!")
```
### `:Disconnect(PLAYER_INSTANCE)`
#### Disconnects the requested player from the server.
```lua
local Player = Players:GetPlayerFromCharacter(Character)
FZZYService:Disconnect(Player)
```
### `:getServerType()`
#### Returns the current Server's Type. (VIP, Reserved, Standard)
```lua
local ServerType = FZZYService:getServerType()
print("This server is a "..ServerType.." server!")
```
### `:defineSpawn(STRING)`
#### Adds a function string to a list of arrays, this is required before using the `:spawn()` function.
```lua
FZZYService:defineSpawn("STRING")
```
### `:spawn(STRING, FUNCTION)`
#### Runs a function.
```lua
FZZYService:spawn("STRING", function()
  print("Hello World!")
end)
```
### `:CastRay(RAY_ORIGIN, RAY_DIRECTION, RAY_PARENT, FILTER_TYPE, FILTERED_INSTANCES_TABLE)`
#### Casts a ray with the following Arguments as information.
```lua
FZZYService:CastRay(SecondPart.Position, Vector3.new(0, -100, 0), SecondPart.Parent, Enum.RaycastFilterType.Blacklist, {SecondPart.Parent})
```
### `:getPlayerFromCharacter(CHARACTER_INSTANCE)`
#### Returns the character's respective player.
```lua
local Player = FZZYService:getPlayerFromCharacter(Character)
print(Player.Name)
```
### `:getGameId()`
#### Returns the game's global id.
```lua
local GameId = FZZYService:getGameId()
print(GameId)
```
### `:Weld(PART_0, PART_1, PART_TO_INSERT_WELD_INTO)`
#### Welds 2 parts together. Returns with the Weld if a `local` is inserted.
```lua
FZZYService:Weld(FirstPart, SecondPart, FirstPart)
```
