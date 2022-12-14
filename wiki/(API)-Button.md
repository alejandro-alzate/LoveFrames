# Information
The button object functions much like a button you would see in a modern day GUI.

## Example Use
```lua
function love.load()
    loveframes = require("loveframes")
         
    local button = loveframes.Create("button")
    button:SetWidth(200)
    button:SetText("Button")
    button:Center()
    button.OnClick = function(object, x, y)
        object:SetText("You clicked the button!")
    end
    button.OnMouseEnter = function(object)
        object:SetText("The mouse entered the button.")
    end
    button.OnMouseExit = function(object)
        object:SetText("The mouse exited the button.")
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
## OnClick 
Called every time the object is clicked 
> Arguments passed: self [object], mouse x [number], mouse y [number]

```lua
local button = loveframes.Create("button")
button.OnClick = function(object)
    print("The button was clicked!")
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

## SetClickable
Sets whether or not the object is clickable

```lua
object:SetClickable(clickable[bool])
```

## GetClickable
Gets whether or not the object is clickable 

> Returns 1 value: clickable [boolean]

```lua
local clickable = object:GetClickable()
```

## SetEnabled
Sets whether or not the object is enabled

```lua
object:SetEnabled(enabled[bool])
```

## GetEnabled
Gets whether or not the object is enabled 

> Returns 1 value: enabled [bool]

```lua
local enabled = object:GetEnabled()
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
## More Info
For an example of Button Group and Buttons with image (not Image Button) see https://github.com/linux-man/LoveFrames/blob/master/demo/examples/buttongroup.lua
