# wrapper.newParagraph()

|                      | &nbsp; 
| -------------------- | ---------------------------------------------------------------
| __Type__             | [function](http://docs.coronalabs.com/api/type/Function.html)
| __Library__          | [wrapper.*](Readme.markdown)
| __Return value__     | [display object](https://docs.coronalabs.com/api/type/DisplayObject/index.html)



## Overview

What you get with the newParagraph function is a corona display-group with text objects inside.

Use `\n` within your text to force line breaks.

The fontColor must be set with:
``````lua
myParagraph:setTextColor({r,g,b,[alpha]})
``````
Text changes:<br>
In fact that a new text must be wrapped anyway, you have to generate a new object for text changes.

Study the sample-code and the parameter-list for usage.


## Syntax

	wrapper.newParagraph( parameter )


The `parameter` table contains the following properties:

#### text <small>(required)</small>
_[string](https://docs.coronalabs.com/api/library/string/find.html)._ The text to display.

#### width <small>(optional)</small>
_[number](https://docs.coronalabs.com/api/type/Number.html)._ The desired width of the paragraph. 

#### height <small>(optional)</small>
_[number](https://docs.coronalabs.com/api/type/Number.html)._ The desired height of the paragraph. If a height is set, the fontsize will be ignored and appointed automatically. Do not set the height if you want a fix font size.

#### font <small>(optional, default: system font)</small>
_[string](https://docs.coronalabs.com/api/library/string/find.html)._ The desired font.

#### fontSize <small>(optional)</small>
_[number](https://docs.coronalabs.com/api/type/Number.html)._ The desired fontSize. Ignored if height is set. 

#### lineSpace <small>(optional)</small>
_[number](https://docs.coronalabs.com/api/type/Number.html)._ You can increase/decrease the line space with +/- values.

#### alignment <small>(optional, default: "center")</small>
_[string](https://docs.coronalabs.com/api/library/string/find.html)._ Choose "left", "center", "right" or "justify" alignment.

#### fontSizeMin <small>(optional, default: 6)</small>
_[number](https://docs.coronalabs.com/api/type/Number.html)._ This value is the start value for the search of the suitable font size. Increase the number for speed improvement. But use with care, if the text is too long it will maybe not fit your frame if fontSizeMin is set too high.

#### fontSizeMax <small>(optional, default: 0)</small>
_[number](https://docs.coronalabs.com/api/type/Number.html)._ If you want to have a limit for the font-size, here you can set it up. 0 means no limit.

#### incrementSize <small>(optional, default: 1)</small>
_[number](https://docs.coronalabs.com/api/type/Number.html)._ This is the amount of the fontsize raise for searching the suitable font size. Higher numbers will speed up the process, but the result of the calculated fontsize is up to incrementSize-1 smaller as it could be.



## Examples

``````lua
local myParagraph = wrapper.newParagraph(
{
    text = "Wrapper Plugin Sample-Text\n\nCorona's framework dramatically increase productivity. \nTasks like animating objects in OpenGL or creating user-interface widgets take only one line of code, and changes are instantly viewable in the Corona Simulator.",
    width = 200,
    height = 200,   		-- fontSize will be calculated automatically if set 
    font = native.systemFont,   -- make sure the used font is installed on your system
    --fontSize = 30,            -- not needed if height is set 	
    lineSpace = 2,
    alignment  = "center",      -- "left", "right", "center" or "justify" 
    
    -- these Parameters are just relevant if height is set
    fontSizeMin = 4,           	-- for speed tweaking
    incrementSize = 2,          -- for speed tweaking
    fontSizeMax = 30
})

myParagraph.anchorChildren = true
myParagraph.anchorX = 0.5
myParagraph.anchorY = 0
myParagraph.x = display.contentWidth/2
myParagraph.y = 70

myParagraph:setTextColor({0,1,0})


``````
