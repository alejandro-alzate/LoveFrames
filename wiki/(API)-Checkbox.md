# Information
A standard checkbox
## Example Use
```lua
local checkbox = loveframes.Create("checkbox")
```

# Event Callbacks
## OnChanged
Called every time the object becomes checked or unchecked 

> Arguments passed: self [object], checked [boolean]

```lua
local checkbox = loveframes.Create("checkbox")
checkbox:SetText("Checkbox")
checkbox:SetPos(5, 30)
checkbox.OnChanged = function(object, value)
    print(value)
end
```

# Methods
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

## SetChecked
Sets whether the object is checked or not

```lua
object:SetChecked(checked[boolean])
```

## GetChecked
Gets whether the object is checked or not 
> Returns 1 value: checked [boolean]
```lua
local checked = object:GetChecked()
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

## GetBoxSize
Gets the object's box size 

> Returns 2 values: boxwidth [number], boxheight [number]
```lua
local boxwidth, boxheight = checkbox:GetBoxSize()
```

## GetBoxWidth
Gets the object's box width 

> Returns 1 value: boxwidth [number]

```lua
local boxwidth = checkbox:GetBoxWidth()
```

## GetBoxHeight
Gets the object's box height 

> Returns 1 value: boxheight [number]

```lua
local boxheight = checkbox:GetBoxHeight()
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