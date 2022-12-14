# Information
The slider object has a button that can be set to slide vertically or horizontally. The object also has a value that can be changed when it moves and a callback for when it's value changes.

# Example Use

```lua
local frame = loveframes.Create("frame")
frame:SetName("Slider")
frame:SetSize(300, 275)
frame:CenterWithinArea(unpack(demo.centerarea))
         
local slider1 = loveframes.Create("slider", frame)
slider1:SetPos(5, 30)
slider1:SetWidth(290)
slider1:SetMinMax(0, 100)
         
local slider2 = loveframes.Create("slider", frame)
slider2:SetPos(5, 60)
slider2:SetHeight(200)
slider2:SetMinMax(0, 100)
slider2:SetButtonSize(20, 10)
slider2:SetSlideType("vertical")
slider2.Update = function(object, dt)
    object:CenterX()
end
```

# Event Callbacks
## OnValueChanged
Called every time the object's value changes 

> Arguments passed: self [object]

```lua
local slider = loveframes.Create("slider")
slider.OnValueChanged = function(object)
    print("The slider's value changed to : " ..object:GetValue())
end
```

## OnRelease
Called every time the slider button is released from being dragged 

> Arguments passed: self [object]

```lua
local slider = loveframes.Create("slider")
slider.OnRelease = function(object)
    print("The slider button has been released.")
end
```

# Methods
## SetValue
Sets the value of the object

```lua
object:SetValue(value[number])
```

## GetValue
Gets the value of the object 

> Returns 1 value: value [number]

```lua
local value = object:GetValue()
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

## SetDecimals
Sets the amount of decimals the object's value should have.

```lua
object:SetDecimals(decimals[number])
```

## SetButtonSize
Sets size of the object's slider button. 

> Returns 2 values: width [number], height [number]

```lua
local width, height = object:GetButtonSize()
```

## SetSlideType
Sets the slide type of the object. Acceptable arguments are "vertical" or "horizontal".

```lua
object:SetSlideType(slidetype[string])
```

## SetScrollable
Sets whether or not the object should be scrollable via the mouse wheel

```lua
object:SetScrollable(scrollable[boolean])
```

## GetScrollable
Gets whether or not the object should be scrollable via the mouse wheel 

> Returns 1 value: scrollable [boolean]

```lua
local scrollable = object:GetScrollable()
```

## SetScrollIncrease 
Sets the amount to increase the object's value by when scrolling with the mouse wheel

```lua
object:SetScrollIncrease(increase[number])
```

## GetScrollIncrease
Gets the amount to increase the object's value by when scrolling with the mouse wheel 

> Returns 1 value: increase [number]

```lua
local increase = object:GetScrollIncrease()
```

## SetScrollDecrease
Sets the amount to decrease the object's value by when scrolling with the mouse wheel

```lua
object:SetScrollDecrease(decrease[number])
```

## GetScrollDecrease
Gets the amount to decrease the object's value by when scrolling with the mouse wheel 

> Returns 1 value: increase [number]

```lua
local decrease = object:GetScrollDecrease()
```