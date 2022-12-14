# Information

## Example Use
```lua
function love.load()
    loveframes = require("loveframes")

    local grid = loveframes.Create("grid")
    grid:SetPos(5, 30)
    grid:SetRows(5)
    grid:SetColumns(5)
    grid:SetCellWidth(25)
    grid:SetCellHeight(25)
    grid:SetCellPadding(5)
    grid:SetItemAutoSize(true)
    grid:ColSpanAt(1, 1, 2)
    grid:RowSpanAt(1, 1, 2)

    local id = 1

    local button = loveframes.Create("button")
    button:SetSize(15, 15)
    button:SetText(id)
    grid:AddItem(button, 1, 1, 'center')
    id = id + 1

    for i=1, 5 do
        for n=1, 5 do
            if (i > 2 or n > 2) then
                local button = loveframes.Create("button")
                button:SetSize(15, 15)
                button:SetText(id)
                grid:AddItem(button, i, n)
            end
            id = id + 1
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
```

# Event Callbacks
The grid object has no unique event callbacks.

# Methods
## AddItem
Adds an item to the object

```lua
object:AddItem(object[object], row[number], column[number], align['left', 'center', 'right'])
```

## GetItem
Gets an item from the object at the specified row and column 

> Returns 1 value: item [object] or false [boolean] if no item was found

```lua
local item = object:GetItem(row[number], column[number])
```

## SetItemAutoSize
Sets whether or not the object should auto-size its items

```lua
object:SetItemAutoSize(autosize[bool])
```

## GetItemAutoSize
Gets whether or not the object should auto-size its items 

> Returns 1 value: autosize [boolean]

```lua
local autosize = object:GetItemAutoSize()
```

## SetRows
Sets the number of rows the object should have

```lua
object:SetRows(rows[number])
```

## GetRows
Gets the number of rows the object has 

> Returns 1 value: rows [number]

```lua
local rows = object:GetRows()
```

## SetColumns
Sets the number of columns the object should have

```lua
object:SetColumns(columns[number])
```

## GetColumns
Gets the number of columns the object has 

> Returns 1 value: columns [number]

```lua
local columns = object:GetColumns()
```

## SetCellWidth
Sets the width of the object's cells

```lua
object:SetCellWidth(cellwidth[number])
```

## GetCellWidth
Gets the width of the object's cells 

> Returns 1 value: cellwidth [number]

```lua
local cellwidth = object:GetCellWidth()
```

## SetCellHeight
Sets the height of the object's cells

```lua
object:SetCellHeight(cellheight[number])
```

## GetCellHeight
Gets the height of the object's cells 

> Returns 1 value: cellheight [number]

```lua
local cellheight = object:GetCellHeight()
```

## SetCellSize
Sets the size of the object's cells

```lua
object:SetCellSize(cellwidth[number], cellheight[number])
```

## GetCellSize
Gets the size of the object's cells 

> Returns 2 value: cellwidth [number], cellheight [number]

```lua
local cellwidth, cellheight = object:GetCellSize()
```

## SetCellPadding
Sets the padding of the object's cells

```lua
object:SetCellPadding(cellpadding[number])
```

## GetCellPadding
Gets the padding of the object's cells 

> Returns 1 value: cellpadding [number]

```lua
local cellpadding = object:GetCellPadding()
```
## ColSpanAt
Expands the size of the column at position

```lua
object:ColSpanAt(row[number], col[number], size[number])
```
## RowSpanAt
Expands the size of the row at position

```lua
object:RowSpanAt(row[number], col[number], size[number])
```