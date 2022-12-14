Welcome to the documentation for Löve Frames. Here you will find information about the library as well as documentation on how each part of it works including function lists and example code.

# About

This library was created to serve as a functional, efficient GUI library for the LÖVE. The goal of this library is to provide an all in one solution for any GUI needs of LÖVE game developers. This library attempts to achieve this goal by providing a large number of advanced GUI elements as well as methods for their manipulation by the developer. This library also provides a feature rich skinning system that enables the game developer customize the look of his/her GUI elements to suit nearly any design.

# Features

 * A variety of simple and advanced GUI elements seen in modern day GUI systems
 * Ability to create custom Drawing and Updating functions for each GUI element
 * Advanced skinning system that allows for limitless design possiblities by both game developers and players
 * Event detection such as mouse enter and mouse exit
 * Manipulation methods for each GUI element to allow customizable behavior

# Installation

## Step 1
 1. Download the source from the repo. 
 2. Place the source in a folder of it's own and then place that folder anywhere within your project.

## Step 2
Now you will need to add a few Löve Frames functions to your LÖVE callbacks. Open your project's `main.lua` file. Then place the following function calls into the proper LÖVE callbacks:

 * `loveframes.update(dt)`
 * `loveframes.draw()`
 * `loveframes.mousepressed(x, y, button)`
 * `loveframes.mousereleased(x, y, button)`
 * `loveframes.keypressed(key, isrepeat)`
 * `loveframes.keyreleased(key)`
 * `loveframes.textinput(text)` (optional)

Now your main callbacks should look something like this:

```lua
function love.update(dt)
             
    -- your code
 
    loveframes.update(dt)
 
end
                 
function love.draw()
 
    -- your code
 
    loveframes.draw()
 
end
 
function love.mousepressed(x, y, button)
 
    -- your code
 
    loveframes.mousepressed(x, y, button)
 
end
 
function love.mousereleased(x, y, button)
 
    -- your code
 
    loveframes.mousereleased(x, y, button)
 
end
 
function love.keypressed(key, scancode, isrepeat)
 
    -- your code
 
    loveframes.keypressed(key, isrepeat)
 
end
 
function love.keyreleased(key)
 
    -- your code

    loveframes.keyreleased(key)
 
end

-- Used by text input object

function love.textinput(text)

    -- your code

    loveframes.textinput(text)

end
```

## Step 3
Now that you have successfully installed Löve Frames, you can load Löve Frames by requiring it. Simply place this piece of code in your `love.load()` function in `main.lua` :

```lua
loveframes = require("path.to.loveframes")
```

And then replace **path.to.loveframes** with the actual path that you have installed Löve Frames to. For example, `libraries.loveframes` or `libs.loveframes`. If you followed all of the steps above correctly, Löve Frames should now be loaded into your project when you launch it.

# Creating Objects

## The Object Creation Function
Creating a Löve Frames object is quite simple. Just use the `loveframes.Create` function and specify what type of object you want to create as the first argument. For example, if you wanted to create a button you would do something like this:

```lua
local button = loveframes.Create("button")
button:SetPos(10, 10)
```

The above code would create a button and place it at the coordinates 10, 10.

## Parenting Objects
Objects can be parented to other objects in order to create more organized, advanced gui layouts. To parent an object to another object you can either specify a parent object as the second argument in `loveframes.Create`, or you can use the `SetParent` method. Here is an example of both parenting methods:

```lua
local parentframe = loveframes.Create("frame")
 
-- method 1 using loveframes.Create
local button1 = loveframes.Create("button", parentframe)
button1:SetPos(5, 35)
 
-- method 2 using SetParent
local button2 = loveframes.Create("button")
button2:SetParent(parentframe)
button2:SetPos(5, 35)
```
**Only Frames, Panels and Lists can be parents. Other objects - as Collapsible Category - have other ways of "parenting".**

# Using the State System
Löve Frames has a built-in state system that allows the developer to restrict object activity to certain states. For example, if you have a game with a mainmenu state, and you want to create a frame that will only be shown during that state, you could do something like this:

```lua
loveframes.SetState("mainmenu")
                 
local frame = loveframes.Create("frame")
frame:SetName("Mainmenu Frame")
frame:Center()
frame:SetState("mainmenu")
```
        
The above code would set Löve Frames's state to `mainmenu` and create a frame object that will only be shown during that state. To restore Löve Frame's state to the default state, you can do the following:

```lua
loveframes.SetState("none")
```

Optionally, you can define callback functions to manage state events:
```lua
loveframes.SetStateOnOpenCallback("mainmenu", stateOnOpen)
loveframes.SetStateOnCloseCallback("mainmenu", stateOnClose)

stateOnClose = function(currentState, newState)
	print("Closing "..currentState.." before opening "..newState)
end
stateOnOpen = function(currentState, oldState)
	print("Opening "..currentState.." after closing "..oldState)
end
```