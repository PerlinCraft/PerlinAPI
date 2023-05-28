# PerlinAPI

Welcome to this modding API! Lets get started!

Basic knowledge of Lua and ROBLOX Scripting is required for this course.

If your just coming across this repository and don't know what PerlinCraft is you can check <a href="https://web.roblox.com/games/13473011206/PerlinCraft">this</a> out.

I recommend reading the ROBLOX Studio documentation <a href="https://create.roblox.com/docs">here</a> if you dont know how to use ROBLOX Studio.

Example projects are avaliable <a href="https://perlincraft.github.io/PerlinExamples">here</a>

You can download this documentation to read it offline.


# #1: PerlinCraft API Basics and More

Controls:

To open the mod executor click semicolon (;) on your keyboard.

Lets get into the basics.

## Hello world

To make a hello world program in PerlinCraft you can open up the mod executor and enter this:
```lua
_G.Shout("Hello, world!")
```
## Creating Parts

All the "Objects" in the game are stored in a variable called _G.World.

It is recommended to use _G.World over workspace. Because player-placed objects are stored there.

Lets create a part at the position of a player.

```lua
_G.CreatePart(_G.GetPlayerPos("username"), Vector3.new(3, 3, 3), _G.World)
```
The first argument in this function is the position of part. 

We are using a function to get a player's position.

The second argument is the size of the part. And last of all is the parent of the part.

## Spawning Built-in objects

So far the built in objects in PerlinCraft are the Zombie and Jeep.

You will need to use CFrames to spawn these things we will spawn them at a players CFrame here

These functions will return the object to so you can save it into a variable.

```lua
-- Zombie
_G.SpawnZombie(_G.GetPlayerCF("username"), _G.World)
_G.SpawnZombie(pos, parent)

-- Jeep
_G.SpawnJeep(_G.GetPlayerCF("username"), _G.World)
_G.SpawnJeep(pos, parent)

```

You can spawn other type of objects with this special function. You must know the object name.

```lua
_G.SpawnObject(objectName, cframe, parent)
```

To get the names of all types of objects you can use this function.
```lua
_G.ObjectTypes()
```
It does not return any value but it instead prints a list of the objects in the message header.

(Where you ran Hello, world!)

## Player Functions

So far about players you learned about GetPlayerCF() and GetPlayerPos().

Now its time for some more player functions!

Here is how you can kick a player out of the server:

```lua
_G.KickPlayer("name", "reason")
```

Here is how you can get the player object itself. This can be very useful.

```lua
_G.GetPLayer("name")
```

You can get all the players online too.

```lua
_G.GetPlayers()
```
You can kick all the players with the KickAllPlayers() function. This can be useful for shutting a server down.
```lua
_G.KickAllPlayers()
```

You can also teleport players using a CFrame!

```lua
-- Teleport a single player
_G.TeleportPlayer("username", cframe)

-- Teleport all players
_G.TeleportAllPlayers(cframe)

```

## World functions

Manage the world with these functions.

Create an explosion.

```lua
_G.CreateExplosion(_G.GetPlayerPos("username"), _G.World)
_G.CreateExplosion(pos, parent)
```
Clear object in the world that are not from world generation

```lua
_G.ClearObjects()
```


# #2: Tips and Tricks

## World Protection

Never call _G.World:ClearAllChildren() as that will also remove the world itself.

If you want to create a custom minigame map I suggest you test it first in a private server.

## Creating Parts

The "_G.CreatePart()" function also returns the part. This can be useful for changing more properties of the part.

## Loops

You can reset your character to stop an infinite loop from a mod (If you ran it)


# End of the documentation

Thanks for using this short introduction to PerlinCraft modding :D