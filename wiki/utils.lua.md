# Information

Love Frames utils.lua houses various functions, most of which are meant for internal use.

# Functions

## SetActiveSkin
Sets the active skin

```lua
loveframes.SetActiveSkin(name[string])
```

## GetActiveSkin
Gets the active skin 

> Returns 1 value: active skin [string]

```lua
local activeskin = loveframes.GetActiveSkin()
```

## BoundingBox
Used to check for collisions of two rectangles 

*Note: I take no credit for this function*

> Returns 1 value: collision [boolean] 

```lua
local col = loveframes.BoundingBox(x1, x2, y1, y2, w1, w2, h1, h2)
```

## GetCollisions
Get what objects the mouse cursor is colliding with 
> Returns 1 value: objects [table]

```lua
local cols = loveframes.GetCollisions(object, t)
```

## GetAllObjects
Gets all active Love Frames objects 

> Returns 1 value: objects [table]

```lua
local objects = loveframes.GetAllObjects(object, t)
```

## GetDirectoryContents
Gets the contents of a directory recursively 

> Returns 1 value: directory contents [table]

```lua
local contents = loveframes.GetDirectoryContents(dir, t)
```

## Round
Used to round numbers 

*Note: I take no credit for this function*

> Returns 1 value: rounded number [number] 

```lua
local roundednumber = loveframes.Round(num, idp)
```

## SplitString
Splits a string into a table by the given pattern 

*Note: I take no credit for this function*

> Returns 1 value: table [table] 

```lua
local table = loveframes.SplitString(str, pat)
```

## RemoveAll
Removes all active Love Frames objects

```lua
loveframes.RemoveAll()
```

## TableHasKey
Checks to see if a table has a specific key 
> Returns 1 value: haskey [boolean]

```lua
local haskey = loveframes.TableHasKey(table, key)
```

## Error
Displays an error message as a Love Frames error

```lua
loveframes.Error(message)
```

## GetCollisionCount
Gets the total number Love Frames objects colliding with the mouse 
> Returns 1 value: collisioncount [number]

```lua
local colcount = loveframes.GetCollisionCount()
```

## GetHover
Returns true if the mouse is colliding with a visible Love Frames objetct, false if not 
> Returns 1 value: hover [boolean]

```lua
local hover = loveframes.GetHover()
```
## RectangleCollisionCheck
Checks for collisions between two rectangles 

> Returns 1 value: collision [boolean]

```lua
local col = loveframes.RectangleCollisionCheck(rect1[table], rect2[table])
```
## DeepCopy
Copies a table 

> Returns 1 value: newtable [table]

```lua
local newtable = loveframes.DeepCopy(original_table[table])
```