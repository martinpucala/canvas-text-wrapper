canvas-text-wrapper
=================
v0.6.5


## Syntax
```
CanvasTextWrapper(HTMLCanvasElement, String [, options]);
```

```options``` - is an object with the following available properties and values:

- ```font:``` (String) - text style that includes font size (in px), font weight, font family, etc. Similar to CSS font
 shorthand property
- ```lineHeight:``` (String or Number) - Number means 'n' times font size where 1 is equivalent to '100%'. Also the property can be set in "%" or "px" using String
- ```textAlign: "left" | "center" | "right"``` - horizontal alignment of each line
- ```verticalAlign: "top" | "middle" | "bottom"``` - vertical alignment for the whole text block
- ```paddingX:``` (Number) - horizontal padding (in px) set equally on both, left and right sides
- ```paddingY:``` (Number) - vertical padding (in px) set equally on both, top and bottom sides
- ```fitParent:``` (Boolean) - if enabled, text will fit canvas container's width/height instead of canvas own 
width/height
- ```lineBreak: "auto" | "word"``` - text split rule. When using ```"auto"```, text goes to a next line on a whole word when there's no more room. If ```"word"``` is set as value, each next word will be placed on a new line.
- ```sizeToFill:``` (Boolean) - ignore given font size and line height and resize text to fill its padded container
- ```strokeText:``` (Boolean) - outline text based on context configuration
- ```justifyLines:``` (Boolean) - if enabled, all lines match the same width with flexed spaces between words (one-word lines are ignored).
- ```allowNewLine:``` (Boolean) if enabled, the text breaks on every new line character "\n" otherwise it'll be considered as a space
- ```renderHDPI:``` (Boolean) if enabled, text is rendered based on device pixel ratio for high-DPI screens

NOTE: if a single word is too long to fit the width with specified font size, it will break on any letter unless ```sizeToFill``` option is enabled.

## Default options
```javascript
   { 
        font: "18px Arial, sans-serif",
        lineHeight: 1,
        textAlign: "left",
        verticalAlign: "top",
        paddingX: 0,
        paddingY: 0,
        fitParent: false,
        lineBreak: "auto",
        strokeText: false
        sizeToFill: false,
        allowNewLine: true,
        justifyLines: false,
        renderHDPI: true
    }
```

## Usage
Configure context settings properties such as "fillStyle", "lineWidth" or "strokeStyle" before using CanvasTextWrapper like so:

```javascript
var CanvasTextWrapper = require('canvas-text-wrapper').CanvasTextWrapper;

var canvas = document.getElementById("#canvasText");
canvas.width = 200;
canvas.height = 200;
context = canvas.getContext("2d");
context.lineWidth = 2;
context.strokeStyle = "#ff0000";
CanvasTextWrapper(canvas, "Hello");    // default options will apply
```

## Test
In terminal go to ```canvas-text-wrapper``` folder do ```npm i``` and run ```npm t```. 
NOTE: Test requires ```beefy``` to be installed globally [beefy](http://didact.us/beefy/)

## Examples
[see here](http://namniak.github.io/canvas-text-wrapper/)

## Installation
```sh
bower install canvas-text-wrapper
npm i canvas-text-wrapper --save
```