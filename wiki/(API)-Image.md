# Information
The image object is basically just an `image` with customizable color.

## Example Use

```lua
function love.load()
    loveframes = require("loveframes")

    local image = loveframes.Create("image")
    image:SetImage("magic.jpg")
    image:SetPos(0, 0)
    image:SetSize(love.graphics.getDimensions())

    local panel = loveframes.Create("panel")
    panel:SetPos(5, 160)
    panel:SetSize(128, 170)

    local text1 = loveframes.Create("text", panel)
    text1:SetPos(5, 5)
    text1:SetText("Orientation: ")

    local slider1 = loveframes.Create("slider", panel)
    slider1:SetPos(5, 20)
    slider1:SetWidth(118)
    slider1:SetMinMax(0, loveframes.Round(math.pi * 2, 5))
    slider1:SetDecimals(5)
    slider1.OnValueChanged = function(object)
        image:SetOrientation(object:GetValue())
    end

    text1.Update = function(object, dt)
        local value = slider1:GetValue()
        local max = slider1:GetMax()
        local progress = value/max
        local final = loveframes.Round(360 * progress)
        object:SetText("Orientation: " ..final)
    end

    local text2 = loveframes.Create("text", panel)
    text2:SetPos(5, 40)
    text2:SetText("Scale")

    local slider2 = loveframes.Create("slider", panel)
    slider2:SetPos(5, 55)
    slider2:SetWidth(118)
    slider2:SetMinMax(.5, 2)
    slider2:SetValue(1)
    slider2:SetDecimals(5)
    slider2.OnValueChanged = function(object)
        image:SetScale(object:GetValue(), object:GetValue())
    end

    text2.Update = function(object, dt)
        object:SetText("Scale: " ..slider2:GetValue())
    end

    local text3 = loveframes.Create("text", panel)
    text3:SetPos(5, 75)
    text3:SetText("Offset")

    local slider3 = loveframes.Create("slider", panel)
    slider3:SetPos(5, 90)
    slider3:SetWidth(118)
    slider3:SetMinMax(0, 50)
    slider3:SetDecimals(5)
    slider3.OnValueChanged = function(object)
        image:SetOffset(object:GetValue(), object:GetValue())
    end

    text3.Update = function(object, dt)
        object:SetText("Offset: " ..slider3:GetValue())
    end

    local text4 = loveframes.Create("text", panel)
    text4:SetPos(5, 110)
    text4:SetText("Shear")

    local slider4 = loveframes.Create("slider", panel)
    slider4:SetPos(5, 125)
    slider4:SetWidth(118)
    slider4:SetMinMax(0, 40)
    slider4:SetDecimals(5)
    slider4.OnValueChanged = function(object)
        image:SetShear(object:GetValue(), object:GetValue())
    end

    text4.Update = function(object, dt)
        object:SetText("Shear: " ..slider4:GetValue())
    end

    local checkbox5 = loveframes.Create("checkbox", panel)
    checkbox5:SetText("Stretched")
    checkbox5:SetPos(5, 150)
    checkbox5.OnChanged = function(object, value)
        image.stretch = value
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
The image object has no unique event callbacks.

# Methods
## SetImage
Sets the object's image 

> Note: The argument in this function can be a path to an image or an image already created with `love.graphics.newImage`.

```lua
object:SetImage(image[string or image])
```

## GetImage
Gets the object's image 

> Returns 1 value: image [image]

```lua
local image = object:GetImage()
```

## SetColor
Sets the objects color 

```lua
object:SetColor(r[number], g[number], b[number], a[number])
```

## GetColor
Gets the objects color 

> Returns 4 values: r [number], g [number], b [number], a [number]

```lua
local r, g, b, a = object:GetColor()
```

## SetOrientation
Sets the objects orientation 

```lua
object:SetOrientation(orientation[number])
```

## GetOrientation
Gets the objects orientation 

> Returns 1 value: orientation [number]

```lua
local orientation = object:GetOrientation()
```

## SetScaleX
Sets the object's x scale 

```lua
object:SetScaleX(scalex[number])
```

## GetScaleX
Gets the object's x scale 

> Returns 1 value: scalex [number]

```lua
local scalex = object:GetScaleX()
```

## SetScaleY
Sets the object's y scale 

```lua
object:SetScaleY(scaley[number])
```

## GetScaleY
Gets the object's y scale 

> Returns 1 value: scaley [number]

```lua
local scaley = object:GetScaleY()
```

## SetScale
Sets the object's x and y scale 

```lua
object:SetScale(scalex[number], scaley[number])
```

## GetScale
Gets the object's x and y scale 

> Returns 2 values: scalex [number], scaley [number]

```lua
local scalex, scaley = object:GetScale()
```

## SetOffsetX
Sets the object's x offset 

```lua
object:SetOffsetX(offsetx[number])
```

## GetOffsetX
Gets the object's x offset 

> Returns 1 value: offsetx [number]

```lua
local offsetx = object:GetOffsetX()
```

## SetOffsetY
Sets the object's y offset 

```lua
object:SetOffsetY(offsety[number])
```

## GetOffsetY
Gets the object's y offset 

> Returns 1 value: offsety [number]

```lua
local offsety = object:GetOffsetY()
```

## SetOffset
Sets the object's x and y offsets 

```lua
object:SetOffset(offsetx[number], offsety[number])
```

## GetOffset
Gets the object's x and y offsets 

> Returns 2 value: offsetx [number], offsety [number]

```lua
local offsetx, offsety = object:GetOffset()
```

## SetShearX
Sets the object's x shear 

```lua
object:SetShearX(shearx[number])
```

## GetShearX
Gets the object's x shear 

> Returns 1 value: shearx [number]

```lua
local shearx = object:GetShearX()
```

## SetShearY
Sets the object's y shear 

```lua
object:SetShearY(sheary[number])
```

## GetShearY
Gets the object's y shear 

> Returns 1 value: sheary [number]

```lua
local sheary = object:GetShearY()
```

## SetShear
Sets the object's x and y shear 

```lua
object:SetShear(shearx[number], sheary[number])
```

## GetShear
Gets the object's x and y shear 

> Returns 2 values: shearx [number], sheary [number]

```lua
local shearx, sheary = object:GetShear()
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