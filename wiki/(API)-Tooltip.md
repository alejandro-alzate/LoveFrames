# Information
The tooltip object displays text when the mouse cursor hovers over an object it has been asigned to.

# Example Use

```lua
local panel = loveframes.Create("panel")
 
local tooltip = loveframes.Create("tooltip")
tooltip:SetObject(panel)
tooltip:SetPadding(10)
tooltip:SetText("This is a panel object.")
```

# Event Callbacks
The tooltip object has no unique event callbacks.

# Methods
## SetFollowCursor
Sets whether the object should follow the mouse cursor when it is visible or not

```lua
object:SetFollowCursor(followcursor[boolean])
```

## SetObject
Sets the object of the tooltip. The tooltip will make itself visible when the object specified is in a hover state.

```lua
object:SetObject(object[object])
```

## SetText
Sets the object's text. 

> Note: You can use color formatted tables of text with this method the same way you would with the text object.

```lua
object:SetText(text[string or table])
```

## SetTextMaxWidth
Sets the max width the object's text will be before wrapping itself. 

> Note: Set to 0 to disable wrapping

```lua
object:SetTextMaxWidth(maxwidth[number])
```

## SetOffsets
Sets the object's x and y offsets
```lua
object:SetOffsets(xoffset[number], yoffset[number])
```
## SetPadding
Set's the object's padding
```lua
object:SetPadding(padding[number])
```
## SetFont
Set's the object's font
```lua
object:SetFont(font[font])
```