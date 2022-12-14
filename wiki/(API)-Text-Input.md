# Information
The text input object receives text from the user via keyboard. The text input object supports both single-line and multi-line input.

## Example Use

```lua
function love.load()
    loveframes = require("loveframes")

    local textinput = loveframes.Create("textinput")
    textinput:SetPos(5, 30)
    textinput:SetWidth(490)
    textinput:SetFont(love.graphics.newFont(12))
    textinput.OnEnter = function(object)
        if not textinput.multiline then
            object:Clear()
        end
    end

    local togglebutton = loveframes.Create("button")
    togglebutton:SetPos(5, 60)
    togglebutton:SetWidth(490)
    togglebutton:SetText("Toggle Multiline")
    togglebutton.OnClick = function(object)
        if textinput.multiline then
            togglebutton:SetPos(5, 60)
            textinput:SetMultiline(false)
            textinput:SetHeight(25)
            textinput:SetText("")
        else
            togglebutton:SetPos(5, 335)
            textinput:SetMultiline(true)
            textinput:SetHeight(300)
            textinput:SetText("")
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

function love.keypressed(key, scancode, isrepeat)
    loveframes.keypressed(key, isrepeat)
end

function love.keyreleased(key)
    loveframes.keyreleased(key)
end

function love.textinput(text)
    loveframes.textinput(text)
end
```

# Event Callbacks
## OnEnter
Called when enter/return is pressed when the object has focus. 

> Arguments passed: self [object], self text [string]

```lua
local textinput = loveframes.Create("textinput")
textinput.OnEnter = function(object, text)
    print(text)
end
```

## OnTextChanged
Called when the object's text is changed. 

> Arguments passed: self [object], text entered [string] or modifier key [string]

```lua
local textinput = loveframes.Create("textinput")
textinput.OnTextChanged = function(object, text)
    print(text)
end
```

## OnFocusGained
Called when the object gains focus. 

> Arguments passed: self [object]

```lua
local textinput = loveframes.Create("textinput")
textinput.OnFocusGained = function(object)
    print("The object has gained focus.")
end
```

## OnFocusLost
Called when the object loses focus. 

> Arguments passed: self [object]

```lua
local textinput = loveframes.Create("textinput")
textinput.OnFocusLost = function(object)
    print("The object has lost focus.")
end
```

# Methods

## SetTextOffsetX
Sets the object's text x offset

```lua
object:SetTextOffsetX(xoffset[number])
```

## SetTextOffsetY
Sets the object's text y offset

```lua
object:SetTextOffsetY(yoffset[number])
```

## SetFont
Sets the object's font

```lua
object:SetFont(font[font])
```

## GetFont
Gets the object's font 

> Returns 1 value: font [font]

```lua
local font = object:GetFont()
```

## SetFocus
Sets the object's focus

```lua
object:SetFocus(focus[true])
```

## GetFocus
Gets the object's focus 

> Returns 1 value: focus [boolean]

```lua
local focus = object:GetFocus()
```

## GetIndicatorVisibility 
Gets the object's indicator visibility 

> Returns 1 value: visibility [boolean]

```lua
local indicatorvisibility = object:GetIndicatorVisibility()
```

## SetLimit
Sets the maximum number of characters the object's text can have

```lua
object:SetLimit(limit[number])
```

## SetUsable
Sets what characters can be used in the object's text

```lua
object:SetUsable(usable[table])
```

## GetUsable
Gets what characters can be used in the object's text 

> Returns 1 value: usable [table]

```lua
local usable = object:GetUsable()
```

## SetUnsable
Sets what characters can not be used in the object's text

```lua
object:SetUnusable(unusable[table])
```

## GetUnsable 
Gets what characters can not be used in the object's text 

> Returns 1 value: unusable [table]

```lua
local unusable = object:GetUnsable()
```

## Clear
Clears the object's text

```lua
object:Clear()
```

## SetText
Sets the object's text

```lua
object:SetText(text[string])
```

## GetText
Gets the object's text

```lua
local text = object:GetText()
```

## SetMultiline
Enables or disables multiline input mode

```lua
object:SetMultiline(multiline[bool])
```

## GetMultiline
Gets whether or not the object is using multiline input 

> Returns 1 value: multiline [bool]

```lua
local multiline = object:GetMultiline()
```

## GetTextX
Gets the x position of the object's text 

> Returns 1 value: textx [number]

```lua
local textx = object:GetTextX()
```

## GetTextY
Gets the y position of the object's text 

> Returns 1 value: texty [number]

```lua
local texty = object:GetTextY()
```

## IsAllTextSelected 
Gets whether or not all of the object's text is selected 

> Returns 1 value: alltextselected [bool]

```lua
local alltextselected = object:IsAllTextSelected()
```

## GetLines
Gets the object's line data 

> Returns 1 value: lines [table]

```lua
local lines = object:GetLines()
```

## GetOffsetX
Gets object's x offset 

> Returns 1 value: offsetx [number]

```lua
local offsetx = object:GetOffsetX()
```

## GetOffsetY
Gets object's y offset 

> Returns 1 value: offsety [number]

```lua
local offsety = object:GetOffsetY()
```

## GetIndicatorX
Gets object's indcator x position 

> Returns 1 value: indicatorx [number]

```lua
local indicatorx = object:GetIndicatorX()
```

## GetIndicatorY
Gets object's indcator y position 

> Returns 1 value: indicatory [number]

```lua
local indicatory = object:GetIndicatorY()
```

## ShowLineNumbers
Toggles the line numbers panel

```lua
object:ShowLineNumbers(show_line_numbers[bool])
```


## SetTabReplacement
Sets what characters should be used to replace tab characters

```lua
object:SetTabReplacement(tabreplacement[string])
```

## GetTabReplacement
Gets object's tab replacement 

> Returns 1 value: tab replacement [string]

```lua
local tabreplacement = object:GetTabReplacement()
```

## SetEditable
Sets whether the object is editable or not

```lua
object:SetEditable(editable[bool])
```

## GetEditable
Gets whether the object is editable or not 

> Returns 1 value: editable [bool]

```lua
local editable = object:GetEditable()
```

## SetButtonScrollAmount
Sets the amount that the object's scroll buttons will scroll the object's list items by

```lua
object:SetButtonScrollAmount(scrollamount[number])
```

## GetButtonScrollAmount
Gets the object's scroll button scroll amount 

> Returns 1 value: scrollamount [number]


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

## SetAutoScroll
Sets whether or not the object should autoscroll when in multiline mode

```lua
object:SetAutoScroll(autoscroll[bool])
```

## GetAutoScroll
Gets whether or not the object should autoscroll when in multiline mode 

> Returns 1 value: autoscroll [boolean]

```lua
local autoscroll = object:GetAutoScroll()
```

## SetRepeatDelay
Sets the delay before the object begins to repeat the key that is being held down

```lua
object:SetRepeatDelay(delay[number])
```

## GetRepeatDelay
Gets the object's repeat delay 

> Returns 1 value: delay [number]

```lua
local delay = object:GetRepeatDelay()
```

## SetValue
Sets the object's value 

> Note: This method is an alias of SetText(text)

```lua
object:SetValue(value)
```

## GetValue
Gets the object's value 

> Returns 1 value: value [string] 

> Note: This method is an alias of GetText()

```lua
local value = object:GetValue()
```

# Internal Methods
These methods are used by the object internally. You should not use them unless you know what you are doing.

## RunKey
Called when a key is pressed and needs to be processed into text. 

```lua
object:RunKey(key[string], unicode[number])
```
## MoveIndicator
Moves the object's indicator 

```lua
object:MoveIndicator(num[number], exact[boolean])
```
## UpdateIndicator
Updates the object's indicator 

```lua
object:UpdateIndicator()
```

## AddIntoText
Adds text into the object's text at a specific location 

```lua
object:AddIntoText(text[string], position[number])
```

## RemoveFromText
Removes a chracter from the object's text 

```lua
object:AddIntoText(position[number])
```

## GetTextCollisions
Gets collisions with the object's text and the mouse cursor 

```lua
object:GetTextCollisions(x[number], y[number])`
```

## PositionText
Positions the object's text 

```lua
object:PositionText()
```

## GetVerticalScrollBody
Gets the object's vertical scroll body 

> Returns 1 value: vscrollbody [object] 

```lua
local vscrollbody = object:GetVerticalScrollBody()
```

## GetHorizontalScrollBody
Gets the object's horizontal scroll body 

>Returns 1 value: hscrollbody [object] 

```lua
local hscrollbody = object:GetHorizontalScrollBody()
```

## HasVerticalScrollBody
Checks if the object has a vertical scroll body 

> Returns 1 value: hasvscrollbody [bool] 

```lua
local hasvscrollbody = object:HasVerticalScrollBody()
```

## HasHorizontalScrollBody
Checks if the object has a horizontal scroll body 

> Returns 1 value: hashscrollbody [bool] 

```lua
local hashscrollbody = object:HasHorizontalScrollBody()
```

## GetLineNumbersPanel
Gets the object's line numbers panel 

> Returns 1 value: panel [object] 

```lua
local panel = object:GetLineNumbersPanel()
```

## GetItemWidth
Gets object's item width 

> Returns 1 value: itemwidth [number] 

```lua
local itemwidth = object:GetItemWidth()
```

## GetItemHeight
Gets object's item height 

> Returns 1 value: itemheight [number] 

```lua
local itemheight = object:GetItemHeight()
```
