# Information
The tabs object functions a lot like the tabs you would find in an internet browser.

# Example Use
```lua
function love.load()
    loveframes = require("loveframes")

    local tabs = loveframes.Create("tabs")
    tabs:SetPos(30, 30)
    tabs:SetSize(490, 265)

    for i=1, 20 do
        local panel = loveframes.Create("panel")
        local text1 = loveframes.Create("text", panel)
        text1:SetText("Tab " ..i)
        text1:SetAlwaysUpdate(true)
        text1.Update = function(object, dt)
            object:Center()
        end
        tabs:AddTab("Tab " ..i, panel, "Tab " ..i)
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
The tabs object has no unique event callbacks.

# Methods
## AddTab
Add a tab to the object. Each tab must have a base object. The base object is the second argument provided. 

The last two arguments of this method are optional and are used to specify callback functions for the tabbutton object that will be created after calling this method. More specifically, these two callbacks are `OnOpened` (called when the tab button becomes active or is "opened") and `OnClosed` (called when the tabbutton becomes inactive or is "closed"). The tabbutton object will provide itself as an argument whenever it calls one of these callbacks.

```lua
object:AddTab(name[string], object[object], tip[string], image[image], onopened[func], onclosed[func])
```

## SwitchToTab
Switches to a different tab

```lua
object:SwitchToTab(tabnumber[number])
```

## SetPadding
Sets the padding of the object

```lua
object:SetPadding(padding[number])
```

## GetPadding
Gets the padding of the object 

> Returns 1 value: padding [number]

```lua
local padding = object:GetPadding()
```

## SetTabHeight
Sets the height of the tab buttons

```lua
object:SetTabHeight(height[number])
```

## GetTabNumber
Gets the object's tab number 

> Returns 1 value: tabnumber [number]

```lua
local tabnumber = object:GetTabNumber()
```

## RemoveTab
Removes a tab from the object's list of tabs

```lua
object:RemoveTab(tabid[number])
```

## SetButtonScrollAmount
Sets the amount that the object's scroll buttons will scroll the object's list items by

```lua
object:SetButtonScrollAmount(scrollamount[number])
```

## GetButtonScrollAmount
Sets the amount that the object's scroll buttons will scroll the object's list items by 

> Returns 1 value: scroll amount [number]

```lua
local scrollamount = object:GetButtonScrollAmount()
```

## SetMouseWheelScrollAmount
Sets the amount that the mouse wheel will scroll the object's list items by

```lua
object:SetMouseWheelScrollAmount(scrollamount[number])
```

## GetMouseWheelScrollAmount
Gets the mouse wheel's scroll amount 

> Returns 1 value: scroll amount [number]

```lua
local scrollamount = object:GetMouseWheelScrollAmount()
```

## SetDTScrolling
Sets whether or not the object should use delta time when calculating how many pixels it's scrollbar needs to move.

```lua
object:SetDTScrolling(dtscrolling[boolean])
```

## GetDTScrolling 
Gets whether or not the object should use delta time when calculating how many pixels it's scrollbar needs to move

> Returns 1 value: dtscrolling [boolean]

```lua
local dtscrolling = object:GetDTScrolling()
```

## SetTabObject
Sets the object of a tab 

```lua
object:SetTabObject(tab_id[number], tab_object[object])
```

# Internal Methods
These methods are used internally. You should not use them unless you know what you are doing.

## AddScrollButtons
Adds scroll buttons to the object. 

```lua
object:AddScrollButtons()
```

## GetWidthOfButtons
Gets the entire width of the object's button 

> Returns 1 value: button width [number] 

```lua
local width = object:GetWidthOfButtons()
```
