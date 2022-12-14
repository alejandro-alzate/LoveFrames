# Information

The panel object has nothing unique about it. It is simply meant to be a parent object for other objects.

# Example Use

```lua
function love.load()
    loveframes = require("loveframes")

    local panel = loveframes.Create("panel")
    panel:SetPos(5, 5)
end

function love.update(dt)
    loveframes.update(dt)
end

function love.draw()
    loveframes.draw()
end
```

# Event Callbacks

The panel object has no unique event callbacks.

# Methods
The panel object has no unique methods.