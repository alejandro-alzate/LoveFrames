# Information
The `base` object is the base parent of all Löve Frames objects. The `base` object is created when Löve Frames is initialized and spans the size of the current window. All of its methods are inherited by every Löve Frames object. 

**You should not directly manipulate this object unless you know what you are doing.**

# Methods

## SetPos
Sets the object's position

> Note: If "true" is specified as a second argument then the object will be centered at the given position

```lua
object:SetPos(x[number], y[number], center[boolean])
```

## SetX
Sets the object's x position 

> Note: If "true" is specified as a second argument then the object will be centered at the given position
```lua
object:SetX(x[number], center[boolean])
```

## SetY
Sets the object's y position

> Note: If "true" is specified as a second argument then the object will be centered at the given position

```lua
object:SetY(y[number], center[boolean])
```

## GetPos
Gets the object's position

> Returns 2 values: object x [number], object y [number]

```lua
local x, y = object:GetPos()
```

## GetX
Gets the object's x position 

> Returns 1 values: object x [number]

```lua
local x = object:GetX()
```

## GetY
Gets the object's y position 

> Returns 1 values: object y [number]

```lua
local y = object:GetY()
```

## GetStaticPosition
Gets the object's static position 

> Returns 2 values: object static x [number], object static y [number]

```lua
local sx, sy = object:GetStaticPosition()
```

## GetStaticX
Gets the object's static x position 

> Returns 1 value: object static x [number]

```lua
local sx = object:GetStaticX()
```

## GetStaticY
Gets the object's static y position 

> Returns 1 value: object static y [number]

```lua
local sy = object:GetStaticY()
```

## Center
Center's the object in the center of it's parent both vertically and horizontally

```lua
object:Center()
```

## CenterX
Center's the object in the center of it's parent horizontally

```lua
object:CenterX()
```

## CenterY
Center's the object in the center of it's parent vertically

```lua
object:CenterY()
```

## SetSize
Sets the object's size

```lua
object:SetSize(width[number], height[number])
```

## SetWidth
Sets the object's width

```lua
object:SetWidth(width[number])
```

## SetHeight
Sets the object's height

```lua
object:SetHeight(height[number])
```

## GetSize
Gets the object's size 

> Returns 2 values: object width[number], object height[number]

```lua
local width, height = object:GetSize()
```

## GetWidth
Gets the object's width

> Returns 1 value: object width[number]

```lua
local width = object:GetWidth()
```

## GetHeight
Gets the object's width 

> Returns 1 value: object height[number]

```lua
local height = object:GetHeight()
```

## SetVisible
Sets whether or not the object is invisble
```lua
object:SetVisible(visible[boolean])
```

## GetVisible
Gets whether or not the object is invisble
```lua
local visible = object:GetVisble()
```

## SetParent
Sets the object's parent (only Frames, Panels and Lists can be parents)
```lua
object:SetParent(parent[object])
```

## GetParent
Gets the object's parent

```lua
local parent = object:GetParent()
```

## Remove
Removes the object
```lua
object:Remove()
```

## SetClickBounds
Restricts the object's ability to be clicked to certain area 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:SetClickBounds(x[number], y[number], width[number], height[number])
```

### GetClickBounds
Gets the object's click boundaries 

> Returns 1 value: click boundaries [table]

```lua
object:SetClickBounds(x[number], y[number], width[number], height[number])
```

## RemoveClickBounds
Removes the object's click boundaries 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:RemoveClickBounds()
```

## IsTopCollision
Checks if the object the top most object in a collision table 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:IsTopCollision()
```

### GetBaseParent
Gets the object's base parent 

> Returns 1 value: base parent [object]

```lua
local baseparent = object:GetBaseParent()
```

## CheckHover
Checks to see if the object should be in a hover state or not 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:CheckHover()
```

## GetHover
Gets whether or not the object is in a hover state 

> Returns 1 value: hover [boolean]

```lua
local hover = object:GetHover()
```

## GetChildren
Returns a table of the object's children 

> Returns 1 value: children [table]

```lua
local children = object:GetChildren()
```

## GetInternals
Returns a table of the object's internals 

> Returns 1 value: internals [table]

```lua
local internals = object:GetInternals()
```

## IsTopList
Checks to see if the object is the top most list object 

> Returns 1 value: is top list [boolean]

```lua
local istoplist = object:IsTopList()
```

## IsTopChild
Checks to see if the object is the top most child among it's parent's children 

> Returns 1 value: is top child [boolean]

```lua
local istopchild = object:IsTopChild()
```

## MoveToTop
Moves the object to the top of it's parent's children

```lua
object:MoveToTop()
```

## SetSkin
Sets the object's skin and it's childrens' skin recursively

```lua
object:SetSkin(skinname[string])
```

## GetSkin
Gets the object's skin 
> Returns 1 value: skin [table]
```lua
local skin = object:GetSkin()
```

## GetSkinName
Gets the object's skin name
> Returns 1 value: skin name [string]
```lua
local skin_name = object:GetSkinName()
```

## SetAlwaysUpdate
Sets whether or not the object should always update. If set to true, the object will update even when not visible.
```lua
object:SetAlwaysUpdate(alwaysupdate[boolean])
```

## GetAlwaysUpdate
Gets whether or not the object should always update 
> Returns 1 value: always update [boolean]
```lua
local alwaysupdate = object:GetAlwaysUpdate()
```

## SetRetainSize
Sets whether or not the object should retain it's size when another object attempts to re-size it
```lua
object:SetRetainSize(retainsize[boolean])
```

## GetRetainSize
Gets whether or not the object should retain it's size when another object attempts to re-size it 

> Returns 1 value: retain size [boolean]

```lua
local retainsize = object:GetRetainSize()
```

## IsActive
Gets whether or not the object is active within it's parent's child table 

> Returns 1 value: active [boolean]

```lua
local active = object:IsActive()
```

## GetParents
Returns a table of the object's parents and it's sub-parents 

> Returns 1 value: parents [table]

```lua
local parents = object:GetParents()
```

## IsTopInternal
Returns true if the object is the top most internal in it's parent's internals table or false if not 
> Returns 1 value: top [boolean]

```lua
local top = object:IsTopInternal()
```

## IsInternal
Returns true if the object is internal or false if not 
> Returns 1 value: internal [boolean]

```lua
local internal = object:IsInternal()
```

## GetType
Gets the type of the object 
> Returns 1 value: type [string]

```lua
local type = object:GetType()
```

## SetDrawOrder
Sets the object's draw order 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:SetDrawOrder(draworder[number])
```

## GetDrawOrder
Gets the object's draw order 

> Returns 1 value: draw order [number]

```lua
local draworder = object:GetDrawOrder()
```

## SetProperty
Sets a property on an object
```lua
object:SetProperty(name[string], value[not_type_specific])
```

## GetProperty
Gets a property on an object 
> Returns 1 value: property [number or string or boolean or table or userdata]
```lua
local property = object:GetProperty(name)
```

## CenterWithinArea
Centers the object within a rectangular area

```lua
object:CenterWithinArea(x[number], y[number], width[number], height[number])
```

## IsInList
Checks to see if an object is parented within a list object 

> Returns 2 values: inlist [boolean], list [object or boolean] 

> Note: The the second value returned is the list that the object is parented to, or false if the object is not in a list

```lua
local inlist, list = object:IsInList()
```

## SetState
Sets the object's state

```lua
object:SetState(state[string])
```

## GetState
Gets the object's state 

> Returns 1 value: state [string]

```lua
local state = object:GetState()
```