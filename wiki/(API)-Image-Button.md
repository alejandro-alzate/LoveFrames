# Information

The image button object is pretty much the same as the button object except it can have an image.

# Example Use

```lua
function love.load()
    loveframes = require("loveframes")

    local imagebutton = loveframes.Create("imagebutton")
    imagebutton:SetImage("magic.jpg")
    imagebutton:SizeToImage()
    imagebutton:SetText("CLICK THE IMAGE")
    imagebutton:CenterWithinArea(0, 0, love.graphics.getDimensions())
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
local imagebutton = loveframes.Create("imagebutton")
imagebutton.OnClick = function(object)
    print("The image button was clicked!")
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
## SetImage
Sets the object's image

```lua
imagebutton:SetImage(image[string (imagepath) or imageobject])
```

## GetImage
Gets the object's image 

> Returns 1 value: image [image]

```lua
local image = imagebutton:GetImage()
```

## SizeToImage
Makes the object the size of it's image

```lua
imagebutton:SizeToImage()
```

## GetImageSize
Gets the object's image size 

> Returns 2 values: imagewidth [number], imageheight [number]

```lua
local imagewidth, imageheight = object:GetImageSize()
```

## GetImageWidth
Gets the object's image width 

> Returns 1 value: imagewidth [number]

```lua
local imagewidth = object:GetImageWidth()
```

## GetImageHeight
Gets the object's image height 

> Returns 1 value: imageheight [number]

```lua
local imageheight = object:GetImageHeight()
```