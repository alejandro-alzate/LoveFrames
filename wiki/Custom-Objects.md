Creating your own custom objects and loading them into Love Frames is quite a simple process. Just follow the steps below.

## Setting Up

To create a custom object to use within Love Frames, you first need create a Lua file for the object. Then place the Lua file in Love Frame's objects directory and open it.

## Creating the Object

To actually create the custom object and have it registered with Love Frames, you need to call `loveframes.NewObject` from within the Lua file that you have created. `loveframes.NewObject` takes 3 arguments. The first argument is a unique id for the object which will be used to create the object with `loveframes.Create`. The second argument is a unique name for the object which will be used by middleclass to actually create the object. The third argument is an optional boolean that specifies whether or not the object should be derrived from the Love Frames base object. When you call `loveframes.NewObject`, it will return the object that it has just created, allowing you to assign custom properties and methods to the object. Below is an example of what a basic custom object might look like:

```lua
return function(loveframes)
---------- module start ----------

local newobject = loveframes.NewObject("customobject", "loveframes_object_custom", true)

function newobject:initialize()
    self.text = "Custom Object"
end

function newobject:update(dt)
    local state = loveframes.state
    local selfstate = self.state

    if state ~= selfstate then
        return
    end

    local visible = self.visible
    local alwaysupdate = self.alwaysupdate

    if not visible then
        if not alwaysupdate then
            return
        end
    end

    local children = self.children
    local parent = self.parent
    local base = loveframes.base
    local update = self.Update

    -- move to parent if there is a parent
    if parent ~= base and parent.type ~= "list" then
        self.x = self.parent.x + self.staticx
        self.y = self.parent.y + self.staticy
    end

    self:CheckHover()

    if children ~= nil then
        for k, v in ipairs(children) do
            v:update(dt)
        end
    end

    if update then
        update(self, dt)
    end
end

function newobject:draw()
    local state = loveframes.state
    local selfstate = self.state

    if state ~= selfstate then
        return
    end

    local visible = self.visible

    if not visible then
        return
    end

    local x = self.x
    local y = self.y
    local width = self.width
    local height = self.height
    local text = self.text
    local children = self.children

    -- set the object's draw order
    self:SetDrawOrder()

    if draw then
        draw(self)
    else
        love.graphics.setColor(1, 1, 1)
        love.graphics.rectangle("fill", x, y, width, height)
        love.graphics.setColor(0, 0, 0)
        love.graphics.print(text, x + 5, y + 5)
    end

    -- loop through the object's children and draw them
    if children ~= nil then
        for k, v in ipairs(children) do
            v:draw()
        end
    end
end

---------- module end ----------
end
```
Now you can call the new object:

```lua
function love.load()
    local co = loveframes.Create("customobject")
    co:SetSize(300, 300)
end
```