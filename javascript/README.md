---
description: "JavaScript is\_an object-based scripting language\_that is lightweight and cross-platform.JavaScript is not compiled but translated. The JavaScript Translator (embedded in browser) is responsible to tr"
---

# Javascript

## JavaScript HTML DOM \(Document Object Model\)

When a web page is loaded, the browser creates a **D**ocument **O**bject **M**odel of the page. With the HTML DOM, JavaScript can access and change all the elements of an HTML document.

The **HTML DOM** model is constructed as a tree of **Objects**:

![The HTML DOM Tree of Objects](../.gitbook/assets/image%20%283%29.png)

Window object - The Browser Object Model

The window object represents a window in browser. An object of window is created automatically by the browser. Window is the object of browser, it is not the object of javascript. The javascript objects are string, array, date etc.

The Browser Object Model \(BOM\) allows JavaScript to "talk to" the browser. All global JavaScript objects, functions, and variables automatically become members of the window object. Global variables are properties of the window object. Global functions are methods of the window object.

* The window.screen object contains information about the user's screen.
*  The `window.location` object can be used to get the current page address \(URL\) and to redirect the browser to a new page.
*  The `window.history` object contains the browsers history.
*  The `window.navigator` object contains information about the visitor's browser.

