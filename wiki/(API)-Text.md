# Information
The text object creates wrappable, character colorable text.

# Example Use
```lua
local loremipsum =
[[http://nikolairesokav.com/
 ---------------------------------------------------
 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean laoreet massa mattis tortor faucibus non congue mauris mattis. Aliquam ultricies scelerisque mi, sit amet tempor metus pharetra vel. Etiam eu arcu a dolor porttitor condimentum in malesuada urna. Mauris vel nulla mi, quis aliquet neque. In aliquet turpis eget purus malesuada tincidunt. Donec rutrum purus vel diam suscipit vehicula. Cras sem nibh, tempus at dictum non, consequat non justo. In sed tellus nec orci scelerisque scelerisque id vitae leo. Maecenas pharetra, nibh eget commodo gravida, augue nisl blandit dui, ut malesuada augue dui nec erat. Phasellus nec mauris pharetra metus iaculis viverra sit amet ut tortor. Duis et viverra magna. Nunc orci dolor, placerat a iaculis non, mattis sed nibh.
 Nulla ut arcu felis, a laoreet tellus. Vivamus ligula nibh, bibendum ut ultrices sed, ullamcorper et est. Pellentesque nisi diam, sollicitudin lacinia fermentum quis, aliquam fermentum elit. Donec egestas vestibulum mollis. Vivamus sollicitudin nisl vestibulum nisi fermentum scelerisque. Nunc enim magna, posuere ornare faucibus a, bibendum vestibulum felis. Etiam laoreet molestie elit, vitae ultrices sem faucibus in. Fusce rutrum convallis lacus, vitae scelerisque eros tincidunt sed. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos.
]]

function love.load()
    loveframes = require("loveframes")

    love.graphics.setBackgroundColor(1, 1, 1)

    local fonts = {}
    for i=10, 30 do
        fonts[i] = love.graphics.newFont(i)
    end

    local list = loveframes.Create("list")
    list:SetPos(5, 30)
    list:SetSize(243, 265)
    list:SetPadding(5)
    list:SetSpacing(5)

    local text1 = loveframes.Create("text")
    text1:SetText(loremipsum)
    text1:SetShadowColor(0.8, 0.8, 0.8, 1)
    list:AddItem(text1)

    local colortext = {}
    for i=1, 49 do
        local r = math.random()
        local g = math.random()
        local b = math.random()
        table.insert(colortext, {color = {r, g, b, 1}, font = fonts[math.random(1, 30)]})
        table.insert(colortext, math.random(1, 1000) .. " ")
    end

    local text2 = loveframes.Create("text")
    text2:SetPos(255, 30)
    text2:SetMaxWidth(243)
    text2:SetText(colortext)

    local shadowbutton = loveframes.Create("button")
    shadowbutton:SetSize(490, 20)
    shadowbutton:SetPos(5, 5)
    shadowbutton:SetText("Toggle Text Shadow")
    shadowbutton.OnClick = function()
        text1:SetShadow(not text1:GetShadow())
        text2:SetShadow(not text2:GetShadow())
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
The text object has no unique event callbacks.

# Formatting Text

## Colors
The text object allows the user to specify color formatted text within a table as the argument to `SetText`. 

Below is an example of how to color format text with the text object:

```lua
local text = {{color = {1, 0, 0}}, "Red ", {color = {0, 1, 0}}, "Green ", {color = {0, 0, 1}}, "Blue"}
object:SetText(text)
```

## Line breaks
To use line breaks in your text you can use one of these methods:
Note that there must be a space before and after each line break character for the text to format properly.

```lua
-- singleline string linebreak
object:SetText("Text with a \n line break")
 
-- multiline string linebreak
local text =
[[
Text with a 
 line break
]]
object:SetText(text)
```

# Text Font

For those who need a fully Unicode compatible font, there is a directive (undocumented) to define a global Text Object Font.

After this line, every created Text Object will use the defined font:

```lua
loveframes.GetActiveSkin().directives.text_default_font = love.graphics.newFont( "Arial.ttf", 12)
```
See [Skins (Usage)](../Skins-(Usage)#using-skins) for more Fonts definitions.

# Methods
## SetText
Sets the object's text 

> Note: The argument can be a string, number, or a table of color formatted text. More information on formatted text can be found toward the top of this page.

```lua
object:SetText(text[string or number or table])
```

## GetText
Gets the object's text 

> Returns 1 value: text [string] 

```lua
local text = object:GetText()
```

## GetFormattedText
Gets the object's formatted text 

> Returns 1 value: text [table] 

> Note: This function returns a table containing both the object's text and data containing how certain parts of that text should be colored.

```lua
local formatted_text = object:GetFormattedText()
```

## DrawText
Draws the object's text 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:DrawText()
```

## SetMaxWidth
Sets the object's maximum width. The object will wrap its text if it exceeds it's maximum width. 

> Note: Set to 0 to disable text wrapping

```lua
object:SetMaxWidth(width[number])
```

## GetMaxWidth
Gets the object's max width 

> Returns 1 value: max width [number]

```lua
local maxwidth = object:GetMaxWidth()
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

## GetLines
Gets the number of lines the object's text uses 

> Returns 1 value: lines [number]

```lua
local lines = object:GetLines()
```

## GetFormattedText
Gets the object's formatted text 

> Returns 1 value: formatted text [table]

```lua
local formattedtext = object:GetFormattedText()
```

## SetIgnoreNewlines
Sets whether the object should ignore \n while formatting it's text

```lua
object:SetIgnoreNewlines(ingorenewlines[bool])
```

## GetIgnoreNewlines
Gets whether the object should ignore \n while formatting it's text 

> Returns 1 value: ignore newlines [bool]

```lua
local ignorenewlines = object:GetIgnoreNewlines()
```

## SetShadow 
Sets whether or not the object should draw it's text twice to create a "shadow" effect 

> Note: Enabling shadows on the text object can be very expensive

```lua
object:SetShadow(shadow[bool])
```

## GetShadow
Gets whether or not the object has shadow drawing enabled 

> Returns 1 value: shadow enabled [bool]

```lua
local shadow = object:GetShadow()
```

## SetShadowOffsets
Sets the x and y offsets of the object's shadow

```lua
object:SetShadowOffsets(xoffset[number], yoffset[number])
```

## GetShadowOffsets
Gets the x and y offsets of the object's shadow 

> Returns 2 values: x offset [number], y offset [number]

```lua
local offsetx, offsety = object:GetShadowOffsets()
```

## SetShadowColor
Sets the color of the object's shadow

```lua
object:SetShadowColor(r[number], g[number], b[number], a[number])
```

## GetShadowColor
Gets the color of the object's shadow 

> Returns 1 value: shadowcolor [table]

```lua
local color = object:GetShadowColor()
```

## SetDefaultColor
Sets the default color of the object's text

```lua
object:SetDefaultColor(r[number], g[number], b[number], a[number])
```

## GetDefaultColor
Gets the default color of the object's text 

> Returns 1 value: defaultcolor [table]

```lua
local defaultcolor = object:GetDefaultColor()
```