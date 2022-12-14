Templates are Lua files that contain a set of properties that can be applied to specific objects when they are created. Below is an example template to give you an idea of how templates work:

```lua
-- template table
local template = {}
 
-- template name
template.name = "Example Template"
 
-- template properties
template.properties = {}
 
template.properties["button"] =
{
    width = 200,
    height = 50
}
 
-- register the template
loveframes.RegisterTemplate(template)
```

The above template example would give every new button object a width of 200 pixels and a height of 50 pixels.

# Creating a Template
Templates consist of a base table containing values that tell them how to work, much like skins. Each base table used for a template layout must contain contain these two keys: `name` and `properties`. Name should be a string containing the name of template and properties should be a table containing sets of properties for objects, similar to the example above. Below is an example of a template layout:

```lua
local template = {}
template.name = "New Template"
template.properties = {}
```

To add properties to a template, all you need to do is create a new table within `template.properties` defined by the name of the object that you want the properties to be applies to. Below is an example of one way this can be done:

```lua
template.properties["button"] = {text = "New button"}
template.properties["panel"] = {x = 10, y = 10}
```

Also, a set of properties can assigned to every object by doing this:

```lua
template.properties["*"] = {x = 10, y = 10}
```

After you have finished adding properties to your template, the last thing to do is to register the template with Love Frames. This can be done by calling the function `loveframes.templates.Register` and specifying your template as an argument. Below is an example of how to do this:

```lua
loveframes.RegisterTemplate(template)
```
After you've setup your template to be registered the last thing that you need to do is make sure that your template file is within the Love Frames templates directory. This directory can be found at: `path/to/loveframes/templates`. After you have done that, your template should load correctly into Love Frames.