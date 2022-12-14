# Properties
Objects have certain variables assigned to them as properties that relate to what they do. Some of these variables are assigned to all objects when they initialize from the default object template. For example, each object has an `x` property, where `x` refers to the object's `x` position on the screen.

# The Default Object Template

The default object template is basically a set of variables that are assigned to all objects when they are initialized. The current layout of this template can be seen below.

```lua
-- default template
loveframes.templates.default =
{
    x = 0,
    y = 0,
    width = 5,
    height = 5,
    staticx = 5,
    staticy = 5,
    draworder = 0,
    internal = false,
    visible = true,
    hover = false,
    alwaysupdate = false,
    retainsize = false,
    calledmousefunc = false,
    skin = nil,
    clickbounds = nil,
    Draw = nil,
    Update = nil,
    OnMouseEnter = nil,
    OnMouseExit = nil,
}
```

You can modify this template in the file `templates.lua`. Any variables added to the default template will be assigned to all Löve Frames objects when they initialize. Most of these variables should not be modified directly unless you know what you are doing.

# Event Callbacks
Objects in Löve Frames have callback functions that handle events for that object. There is a set of event callbacks that any Löve Frames object can use listed below. However, some objects also have additional event callbacks that relate to a specific function that they perform. These additional event callbacks will be listed on that object's information page. 

## OnMouseEnter
Called when the mouse cursor enters an object. 
> Note: The object will pass itself as an argument.

```lua
local panel = loveframes.Create("panel")
panel.OnMouseEnter = function(object)
    print("The mouse entered the object.")
end
```

## OnMouseExit
Called when the mouse cursor exits an object. 
> Note: The object will pass itself as an argument.

```lua
local panel = loveframes.Create("panel")
panel.OnMouseExit = function(object)
    print("The mouse exited the object.")
end
```

## Update
Called by the object every frame. 
> Note: The object will pass itself as the first argument, and deltatime will be passed as the second argument. This function will not be called if the object is not visible unless that object has been set to always update.

```lua
local panel = loveframes.Create("panel")
panel.Update = function(object, dt)
    print(object:GetX(), object:GetY(), dt)
end
```

## Draw
Called when the object is being drawn on the screen. 
> Note: Assigning this function to an object will override the default drawing functions of the object. This is useful for custom object drawing whenever it may be needed. This function will not be called if the object is not visible.

```lua
local panel = loveframes.Create("panel")
panel.Draw = function(object)
    love.graphics.setColor(1, 1, 1)
    love.graphics.rectangle("fill", object:GetX(), object:GetY(), object:GetWidth(), object:GetHeight())
end
```