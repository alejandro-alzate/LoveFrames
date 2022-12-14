# Information
The multichoice object is a dropdown list.

## Example Use
```lua
function love.load()
    loveframes = require("loveframes")

    local multichoice = loveframes.Create("multichoice")
    multichoice:SetPos(5, 5)

    for i=1, 10 do
        multichoice:AddChoice(i)
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

## OnChoiceSelected
Called when a choice is selected 

> Arguments passed: self [object], choice [string]

```lua
local multichoice = loveframes.Create("multichoice")
multichoice.OnChoiceSelected = function(object, choice)
    print(choice .. " was selected.")
end
```

# Methods
## AddChoice
Adds a choice to the object

```lua
object:SetText(text[string])
```

## SetChoice
Sets the current choice of the object 

> Note: Does not call the OnChoiceSelected callback.

```lua
object:SetChoice(choice[string])
```

## SelectChoice
Sets the current choice of the object 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:SelectChoice(choice[string])
```

## SetListHeight
Sets the current choice of the object

```lua
object:SetListHeight(height[number])
```

## SetPadding
Sets the object's padding

```lua
object:SetPadding(padding[number])
```

## SetSpacing
Sets the object's spacing

```lua
object:SetSpacing(spacing[number])
```

## GetChoice
Gets the object's current choice 

> Returns 1 value: choice [string]

```lua
local choice = object:GetChoice()
```

## GetValue
Gets the object's current choice 

> Returns 1 value: value [string] 

> Note: This is the same as GetChoice()

```lua
local value = object:GetValue()
```
## GetChoiceIndex
Gets the object's current choice index

> Returns 1 value: choice [number]

```lua
local choice = object:GetChoiceIndex()
```

## SetText
Sets the object's text

```lua
object:SetText(text[string])
```

## GetText
Gets the object's text 

> Returns 1 value: text [string]

```lua
local text = object:GetText()
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
Sets whether or not the object should use delta time when caclulating how many pixels it's scrollbar needs to move 

```lua
object:SetDTScrolling(dtscrolling[boolean])
```

## GetDTScrolling
Gets whether or not the object should use delta time when caclulating how many pixels it's scrollbar needs to move 

> Returns 1 value: dtscrolling [boolean]

```lua
local dtscrolling = object:GetDTScrolling()
```

## Sort
Sorts the object's choices 

> Note: If no function is specified then the object will use it's default sorting function

```lua
local func = function(a, b) a < b end
object:Sort(func[function])
```

## SetSortFunction
Sets the object's default soring function

```lua
local func = function(a, b) a < b end
object:SetSortFunction(func[function])
```

## GetSortFunction
Gets the object's default soring function

```lua
local func = object:GetSortFunction()
```

## SetSortFunction
Sets the object's default soring function

```lua
local func = function(a, b) a < b end
object:SetSortFunction(func[function])
```

## GetSortFunction
Gets the object's default soring function

```lua
local func = object:GetSortFunction()
```

## RemoveChoice
Removes a choice from the object's list of choices

```lua
object:RemoveChoice(choice[string])
```

## Clear
Removes all choices from the object's list of choices 

```lua
object:Clear()
```

## SetEnabled
Enables or disables the object

```lua
object:SetEnabled(enabled[bool])
```

## GetEnabled
Gets whether or not the object is enabled 

> Returns 1 value: enabled [bool]

```lua
local enabled = object:GetEnabled()
```