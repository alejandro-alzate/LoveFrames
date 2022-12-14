# How Skins Work

A skin is basically a set of functions that dictate how each Löve Frames object is drawn.

# Creating a Skin
 1. Go to the Löve Frames skins directory and create a new folder. 
 2. Name the folder what you want the name of the skin to be. The name of the folder must be exactly what the name of the skin will be. 
 3. Create a file called skin.lua in the folder that you just created. 
 4. Open the skin.lua file that you just created with any text editor and copy and paste the following into the file:
```lua
local skin = {}
 
skin.name = "INSERT SKIN NAME HERE"
skin.author = "INSERT SKIN AUTHOR HERE"
skin.version = "INSERT SKIN VERSION HERE"
```
 5. Replace the value of skin.name with the name of the folder that you created. The value of skin.name must always be the same as the folder of the skin. 
 6. Replace the values of skin.author and skin.version with whatever values you desire. 

Now you can start creating drawing functions for whatever objects you want. 

## Example Usage
Here is an example of what one of these functions would look like:

```lua
function DrawFrame(object)
    love.graphics.setColor(1, 1, 1)
    love.graphics.rectangle("fill", object:GetX(), object:GetY(), object:GetWidth(), object:GetHeight())
end
```

Each object will pass itself to its drawing function as an argument. This allows important values of the object to be accessed such as `x` and `y`. If the skin that you have created does not have a drawing function for a certain object, that object will refer to the default skin drawing functions. For a full list of object drawing functions, please refer to the list further down on this page. 

After you are done creating all of your skin's drawing functions, you will need to end the `skin.lua` file with this piece of code:
```lua
loveframes.RegisterSkin(skin)
```

A skin can also create a table of images within it's folder for easier use withing drawing functions. If you create an images folder within a skin's folder, any images you put in that folder will be added to the skins images table. These images can be access like this:

```lua
function DrawFrame(object)
    love.graphics.setColor(1, 1, 1)
    love.graphics.rectangle("fill", object:GetX(), object:GetY(), object:GetWidth(), object:GetHeight())
    love.graphics.draw(skin.images["imagename.png"], 5, 5)
end
```

So essentialy, any image within the skin's images folder can be accessed via `skin.images["imagename.png"]`. All you would need to do is replace `"imagename"` with the name of the image file and `".png"` with the extension of the image file.

# Using Skins
When an object is created its active skin is set to the current Löve Frames active skin. The Löve Frames active skin can be changed from within `init.lua`. All you need to do is change `loveframes.config["ACTIVESKIN"]` to the name of whatever skin you want to use. If you want to change the active skin withou reloading your project you can do this:

```lua
loveframes.SetActiveSkin("SKINNAME")
```

Doing this will change the active skin. If you only want to change the skin of one object you can do so like this:

```lua
local panel = loveframes.Create("panel")
panel:SetSkin("SKINNAME")
```

Doing this will change the object's skin to the skin specified. It will also change all of the object's children's skins recursively.

Skins properties (and names) are accessible at

```lua
loveframes.skins
```
 
Default skin fonts are

```lua
skin.controls.smallfont = love.graphics.newFont(11)
skin.controls.imagebuttonfont = love.graphics.newFont(15)
```

If you want to change the skin font, you can modify skin.controls.smallfont and skin.controls.imagebuttonfont anytime.

```lua
-- Change fonts on active skin
loveframes.GetActiveSkin().controls.smallfont = love.graphics.newFont( "Arial.ttf", 10)
loveframes.GetActiveSkin().controls.imagebuttonfont = love.graphics.newFont( "Arial.ttf", 15)
```

```lua
-- Change fonts on all registered skins
for _, skin in pairs(loveframes.skins) do
	skin.controls.smallfont = love.graphics.newFont( "Arial.ttf", 10)
	skin.controls.imagebuttonfont = love.graphics.newFont( "Arial.ttf", 15)
end
```


# Drawing Functions
A list of all skin drawing functions:

 * DrawFrame(object)
 * DrawButton(object)
 * DrawCloseButton(object)
 * DrawProgressBar(object)
 * DrawScrollArea(object)
 * DrawScrollBar(object)
 * DrawScrollBody(object)
 * DrawPanel(object)
 * DrawList(object)
 * DrawOverList(object)
 * DrawTabPanel(object)
 * DrawTabButton(object)
 * DrawImage(object)
 * DrawImageButton(object)
 * DrawMultiChoice(object)
 * DrawMultiChoiceList(object)
 * DrawOverMultiChoiceList(object)
 * DrawMultiChoiceRow(object)
 * DrawToolTip(object)
 * DrawText(object)
 * DrawTextInput(object)
 * DrawOverTextInput(object)
 * DrawScrollButton(object)
 * DrawSlider(object)
 * DrawSliderButton(object
 * DrawCheckBox(object)
 * DrawCollapsibleCategory(object)
 * DrawColumnList(object)
 * DrawColumnListHeader(object)
 * DrawColumnListArea(object)
 * DrawOverColumnListArea(object)
 * DrawColumnListRow(object)
 * DrawLineNumbersPanel(object)
 * DrawNumberBox(object)
 * DrawGrid(object)

# Third-Party Skins
A list of skins for Love Frames created by third-party developers:

 * [Gray - by unek](https://github.com/UnekPL/loveframes-gray-theme)
 * [Dark - by unek](https://github.com/UnekPL/loveframes-dark-theme)
 * [Snap - by unek](https://github.com/unek/loveframes-snap-theme)