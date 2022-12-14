# Information
The column list object is similar to the list object except it only displays vertically and has columns. Rows can be added with column specific information.

## Example Use
```lua
function love.load()
    loveframes = require("loveframes")

    local list = loveframes.Create("columnlist")
    list:SetPos(5, 30)
    list:SetSize(490, 265)
    list:AddColumn("Column 1")
    list:AddColumn("Column 2")
    list:AddColumn("Column 3")
    list:AddColumn("Column 4")

    for i=1, 20 do
        list:AddRow("Row " ..i.. ", column 1", "Row " ..i.. ", column 2", "Row " ..i.. ", column 3", "Row " ..i.. ", column 4")
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
## OnRowClicked
Called when a row within the object is clicked 

> Arguments passed: self [object], row [object], row data [table]

```lua
local columnlist = loveframes.Create("columnlist")
columnlist.OnRowClicked = function(parent, row, rowdata)
    for k, v in ipairs(rowdata) do
        print("Column " ..k.. ": " ..v)
    end
end
```

## OnScroll
Called every time the list is scrolled 

> Arguments passed: self [object]

```lua
local list = loveframes.Create("list")
list.OnScroll = function(object)
    print("The list was scrolled.")
end
```

## OnRowRightClicked
Called when a row is right-clicked 

> Arguments passed: parent [object], row [object], data [table]

```lua
local list = loveframes.Create("list")
list.OnRowRightClicked = function(parent, row, data)
    print("A row was right-clicked.")
end
```

## OnRowSelected
Called when a row is selected 

> Arguments passed: parent [object], row [object], data [table]

```lua
local list = loveframes.Create("list")
list.OnRowSelected = function(parent, row, data)
    print("A row was selected.")
end
```

Methods
## AdjustColumns
Adjusts the width of the object's columns 
> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:AdjustColumns()
```

## AddColumn
Adds a column to the object

```lua
object:AddColumn(name[string])
```

## AddRow
Adds a row to the object 

> Note: Each argument is for a column (ex: argument will be for column 1).

```lua
object:AddRow(...[string or number])
```

## GetColumnSize
Gets the width and height of a column 

> Returns 2 values: column width [number], column height [number]

```lua
local w, h = object:GetColumnSize()
```

## SetMaxColorIndex
This is used to specify how many color alternations rows should have. Each row that is added to the object will have a higher color index than the previous row. When it reaches the max color index the color alternator will start at 1 again. These color index ids will be accessible via the column list row drawing function, making it easier to have multicolored rows.

```lua
object:SetMaxColorIndex(max[number])
```

## Clear
Removes all items from the object's list

```lua
object:Clear()
```

## SetAutoScroll
Sets whether the object should auto scroll when a new item is added. If set to true, the object will scroll to the end of itself when a new item is added to it.

```lua
object:SetAutoScroll(autoscroll[boolean])
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

## SetColumnHeight
Sets the height of the object's columns 

```lua
object:SetColumnHeight(height[number])
```

## SetDTScrolling
Sets whether or not the object should use delta time when caclulating how many pixels it's scrollbar needs to move 

```lua
object:SetDTScrolling(dtscrolling[boolean])
```

## GetDTScrolling
Gets whether or not the object should use delta time when calculating how many pixels its scrollbar needs to move 

> Returns 1 value: dtscrolling [boolean]

```lua
local dtscrolling = object:GetDTScrolling()
```

## SelectRow
Selects the specified row

```lua
object:SelectRow(row[object], ctrl[boolean])
```

## DeselectRow
De-selects the specified row

```lua
object:DeselectRow(row[object])
```

##GetSelectedRows
Gets the object's selected rows 

> Returns 1 value: rows [table]

```lua
local rows = object:GetSelectedRows()
```

## SetSelectionEnabled
Sets whether or not the object's rows can be selected

```lua
object:SetSelectionEnabled(enabled[boolean])
```

##GetSelectionEnabled
Gets whether or not the object's rows can be selected 

> Returns 1 value: enabled [boolean]

```lua
local enabled = object:GetSelectionEnabled()
```

## SetMultiselectionEnabled
Sets whether or not multiple rows can be selected at the same time

```lua
object:SetMultiselectionEnabled(enabled[boolean])
```

## GetMultiselectionEnabled
Gets whether or not multiple rows can be selected at the same time 
> Returns 1 value: enabled [boolean]

```lua
local enabled = object:GetMultiselectionEnabled()
```

## RemoveColumn
Removes the specified column

```lua
object:RemoveColumn(id[number])
```

## SetColumnName
Sets the specified column's name

```lua
object:SetColumnName(id[number], name[string])
```

## RemoveRow
Removes the specified row

```lua
object:RemoveRow(id[number])
```

## SetRowColumnText
Sets the text of the specified column on the specified row

```lua
object:SetRowColumnText(text[string], rowid[number], columnid[number])
```

## SetRowColumnData
Sets the text for each column on the specified row

```lua
object:SetRowColumnText(rowid[number], columndata[table])
```

## SizeToChildren
Sets the object's height to the combined height of its children. If max is specified, the object will not become higher than max.

```lua
object:SizeToChildren(max[number])
```

## SetRowsFont
Sets the font of the rows.

```lua
object:SetRowsFont(font[font])
```

## SetRowFont
Sets the font of the row with the provided id.

```lua
object:SetRowFont(font[font], rowid[number])
```