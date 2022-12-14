# Information

The frame object is a mouse-moveable object meant to serve as a base parent for other objects. It has a close button and can have a custom name. It also has a docking functionality that lets it dock onto other frame objects when being moved with the mouse.

## Example Use
```lua
function love.load()
    loveframes = require("loveframes")

    local frame = loveframes.Create("frame")
    frame:SetName("Frame")
    frame:CenterWithinArea(0, 0, love.graphics.getDimensions())
    frame:SetDockable(true)

    local text = loveframes.Create("text", frame)
    text:SetText("This is an example frame.")
    text.Update = function(object, dt)
        object:CenterX()
        object:SetY(40)
    end

    local button = loveframes.Create("button", frame)
    button:SetText("Modal")
    button:SetWidth(100)
    button:Center()
    button.Update = function(object, dt)
        local modal = object:GetParent():GetModal()
        if modal then
            object:SetText("Remove Modal")
            object.OnClick = function()
                object:GetParent():SetModal(false)
            end
        else
            object:SetText("Set Modal")
            object.OnClick = function()
                object:GetParent():SetModal(true)
            end
        end
    end
end

function love.update(dt)
    loveframes.update(dt)
end

function love.draw()
    loveframes.draw()
end

function love.mousepressed(x, y, button)
    loveframes.mousepressed(x, y, button)
end

function love.mousereleased(x, y, button)
    loveframes.mousereleased(x, y, button)
end
```

# Event Callbacks

## OnClose
Called when the object is closed via it's close button 

> Arguments passed: self [object]

```lua
local frame = loveframes.Create("frame")
frame.OnClose = function(object)
    print("The frame was closed.")
end
```

## OnDock
Called when the object docks onto another frame 

> Arguments passed: self [object], dock_object [object]

```lua
local frame = loveframes.Create("frame")
frame.OnDock = function(object, dock_object)
    print("Frame " ..object:GetName().. " has dock onto frame " ..dock_object:GetName().. ".")
end
```

# Methods
## SetName
Sets the object's name

```lua
object:SetName(name[string])
```

## GetName
Gets the object's name 

> Returns 1 value: object name [string]

```lua
local name = object:GetName()
```

## SetDraggable
Sets whether the object can be dragged or not

```lua
object:SetDraggable(draggable[boolean])
```

## GetDraggable
Gets whether the object can be dragged or not 

> Returns 1 value: draggable [boolean]

```lua
local draggable = object:GetDraggable()
```

## SetScreenLocked
Sets whether the frame can be moved passed the boundaries of the window or not

```lua
object:SetScreenLocked(screenlocked[boolean])
```

## GetScreenLocked
Gets whether the frame can be moved passed the boundaries of the window or not 

> Returns 1 value: screen locked [boolean]

```lua
local screenlocked = object:GetScreenLocked()
```

## ShowCloseButton
Sets whether the object's close button should be drawn and clickable or not

```lua
object:ShowCloseButton(show[boolean])
```

## MakeTop
Makes the object the top most object

```lua
object:MakeTop()
```

## SetModal
Used to modal or unmodal the object

```lua
object:SetModal(modal[boolean])
```

## GetModal
Gets whether the object can is modaled or not 

> Returns 1 value: modaled [boolean]

```lua
local modal = object:GetModal()
```

## SetParentLocked
Sets whether the object can or cannot be dragged outside of it's parent's boundaries

```lua 
object:SetParentLocked(parentlocked[boolean])
```

## GetParentLocked
Gets whether the object can or cannot be dragged outside of it's parent's boundaries 

> Returns 1 value: parent locked [boolean]

```lua
local parentlocked = object:GetParentLocked()
```
## SetIcon
Sets the object's icon

```lua
object:SetIcon(icon[string] or icon[image])
```

## GetIcon
Gets the object's icon 

> Returns 1 value: icon [image]

```lua
local icon = object:GetIcon()
```
## SetDockable
Sets whether or not the object can dock onto other frames or be docked by other frames

```lua
object:SetDockable(dockable[bool])
```

## GetDockable
Gets whether or not the object is dockable 

> Returns 1 value: dockable [bool]

```lua
local dockable = object:GetDockable()
```

## SetDockZoneSize
Sets the size of the object's dock zone

```lua
object:SetDockZoneSize(size[number])
```