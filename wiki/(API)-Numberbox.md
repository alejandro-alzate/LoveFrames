# Information
The `numberbox` object allows the user to input a number into a textinput. It also comes with two buttons for increasing or decreasing the number.

# Example Use

```lua
function love.load()
    loveframes = require("loveframes")

    local numberbox = loveframes.Create("numberbox")
    numberbox:SetPos(5, 5)
    numberbox:SetSize(200, 25)
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

## OnValueChanged
Called every time the object's calue changes 

> Arguments passed: self [object], value [number]

```lua
local numberbox = loveframes.Create("numberbox")
numberbox.OnValueChanged = function(object, value)
    print("The object's new value is " ..value)
end
```

# Methods
## SetValue
Sets the object's value

```lua
object:SetValue(value[number])
```

## GetValue
Gets the object's value 

> Returns 1 value: value [number]

```lua
local value = object:GetValue()
```

## SetIncreaseAmount
Sets the object's increase amount

```lua
object:SetIncreaseAmount(amount[number])
```

## GetIncreaseAmount
Gets the object's increase amount 

> Returns 1 value: increaseamount [number]

```lua
local increaseamount = object:GetIncreaseAmount()
```

## SetDecreaseAmount
Sets the object's decrease amount

```lua
object:SetDecreaseAmount(amount[number])
```

## GetDecreaseAmount
Gets the object's decrease amount 

> Returns 1 value: decreaseamount [number]

```lua
local decreaseamount = object:GetDecreaseAmount()
```

## SetMax
Sets the object's maximum value

```lua
object:SetMax(max[number])
```

## GetMax
Gets the object's maximum value 

> Returns 1 value: max [number]

```lua
local max = object:GetMax()
```

## SetMin
Sets the object's minimum value

```lua
object:SetMin(min[number])
```

## GetMin
Gets the object's minimum value 

> Returns 1 value: min [number]

```lua
local min = object:GetMin()
```

## SetMinMax
Sets the object's minimum and maximum values

```lua
object:SetMinMax(min[number], max[number])
```

## GetMinMax
Gets the object's minimum and maximum values 

> Returns 2 values: minimum [number], maximum [number]

```lua
local min, max = object:GetMinMax(min[number], max[number])
```

## ModifyValue
Modifies the object's value 

> Note: This method is used by the object internally. You should not use it unless you know what you are doing.

```lua
object:ModifyValue(type[string])
```