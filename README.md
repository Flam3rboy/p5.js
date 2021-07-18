# p5js-node

p5js-node a Node.js implementation of p5.js for drawing to canvas with nodejs. (using ``node-canvas``)

The [p5js.org](https://p5js.org) website contains an extensive overview of the project, community, documentation, and examples.

### Difference to ``node-p5``
It doesn't use **jsdom** and is actively maintained always up to date fork

## Get Started

Get familiar with p5js: https://p5js.org/get-started

Install p5-node
```
npm i p5js-node
```

#### Usage
```js
const p5 = require("p5js-node");
const path = require("path");
const fs = require("fs");

new p5((p)=>{
	p.setup = function() {
		p.createCanvas(1920,1080);
	};

	p.draw = function() {
		p.background(0);
		p.fill(255);
		p.rect(10,10, 50, 50);
		fs.promises.writeFile(__path.join(__dirname,"..","test.png"), p.canvas.toBuffer());
	};
});
```

## Notice
This is a fork of p5.js for nodejs which doesn't support all browser apis.

The node-canvas api is documented [here](https://www.npmjs.com/package/canvas).

### Not supported (*yet)
* Audio
* WebGL
* Dom
* Acceleration
* Keyboard
* Mouse
* Touch
* Events
* IO (use npm packages instead)


### Changes

```diff
Canvas:
+ toBuffer({ mimeType: "image/png" || "image/jpeg" || "raw", quality: 1 })
Environment:
- describe()
- describeElement()
- fullscreen()
- getURL()
- getURLPath()
- getURLParams()
- getURLParams()
- gridOutput()
- textOutput()
Data:
- storeItem()
- getItem()
- clearStorage()
- removeItem()
DOM:
- select()
- selectAll()
- removeElements()
- changed()
- input()
- createDiv()
- createP()
- createSpan()
- createImg()
- createA()
- createSlider()
- createButton()
- createCheckbox()
- createSelect()
- createRadio()
- createColorPicker()
- createInput()
- createFileInput()
- createVideo()
- createAudio()
- VIDEO
- AUDIO
- createCapture()
- createElement()
- p5.MediaElement
- p5.File
```

## Issues

If you have found a bug in the original p5.js library, you can file it here [here](https://github.com/processing/p5.js/issues). 

If you found a bug in the node implementation, you can file it here [here](https://github.com/x127f/p5/issues). 


## Learning

Check out [p5js.org](https://p5js.org) for lots more! Here are some quick-links to get started learning p5.js.

* [Get Started](https://p5js.org/get-started): Create and run your first sketch!
* [p5.js overview](https://github.com/processing/p5.js/wiki/p5.js-overview): An overview of the main features and functionality of p5.js
* [Reference](https://p5js.org/reference): The functionality supported by p5.js
* [Learn](https://p5js.org/learn): Tutorials and short, prototypical examples exploring the basics of p5.js
* [Forum](https://discourse.processing.org/c/p5js): Ask and answers questions about how to make things with p5.js here
* [Libraries](https://p5js.org/libraries): Extend p5 functionality to interact with HTML, manipulate sound, and more!
* [The Coding Train p5.js Tutorials](https://thecodingtrain.com/beginners/p5js/): A huge trove of tutorials created by Dan Shiffman and friends
* [Community statement](https://p5js.org/community/)
* [Code of conduct](https://github.com/processing/p5.js/blob/main/CODE_OF_CONDUCT.md)
