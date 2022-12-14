# Information
The collapsible category object can is essentially a panel that can be opened or closed and can contain one object as a child.
## Example Use

```lua
function love.load()
    loveframes = require("loveframes")

    local panel = loveframes.Create("panel")
    panel:SetHeight(230)

    local text = loveframes.Create("text", panel)
    text:SetText("Collapsible Category")

    local collapsiblecategory = loveframes.Create("collapsiblecategory")
    collapsiblecategory:SetPos(5, 30)
    collapsiblecategory:SetSize(490, 265)
    collapsiblecategory:SetText("Category 1")
    collapsiblecategory:SetObject(panel)

    text:Center()
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
## OnOpenedClosed 
Called when the object is opened or closed 

> Arguments passed: self [object]

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

## SetObject
Sets the object's object

```lua
local panel = loveframes.Create("panel")
object:SetObject(panel)
```

## GetObject
Gets the object's object 

> Returns 1 value: object [object]

```lua
local selfobject = object:GetObject()
```

## SetClosedHeight
Sets the height of the object when it is closed

```lua
object:SetClosedHeight(height[number])
```

## GetClosedHeight
Gets the height of the object when it is closed 

> Returns 1 value: closedheight [number]

```lua
local closedheight = object:GetClosedHeight()
```

## SetOpen
Sets whether the object is open or not

```lua
object:SetOpen(open[boolean])
```

## GetOpen
Gets whether the object is open or not 

> Returns 1 value: open [boolean]

```lua
local open = object:GetOpen()
```