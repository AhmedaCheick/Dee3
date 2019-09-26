## Part 1: The Fundamentals
---
**D3.js** is a JavaScript library for manipulating documents based on data. D3 helps you bring data to life using HTML, SVG, and CSS

D3 provides developers with the ability to create rich interactive and animated content based on data and tie that content to existing web page elements. <br>
It gives you the tools to create high-performance data dashboards and sophisticated data visualization, and to dynamically update traditional web content.

However, It’s a much longer process than using dedicated charting libraries, but the D3 process is also its **strength**.

### Selecting and Binding
D3 is all about these two. *Selection* is the grouping of elements, whether graphics or traditional divs. <br>
<br>
*Selecting*
<br>
```javascript 
d3.selectAll("circle.a").style("fill", "red").attr("cx", 100);
```

This code takes every circle with class a and turns it red and moves it so that its center is 100 pixels to the right of the left side of our *svg* canvas.

Selections can be made by either `d3.select()` for one element, or `d3.selectAll()` for multiple elements.
<br>
<br>
*Binding*
<br>
<br>
```javascript
d3.selectAll("div.class1").data([4,5,61,3])
``` 
<br>

That line **binds** the array [4,5,61,3] to `div` elements with `class1`. A very **critical** thing to understand and remember here, is that those are rarely equal to each other in length. In some cases we have more divs than data points or vice versa.
<br>
<br>
### The DOM
A web page is structured according to the DOM. It defines a set of nested elements. <br>
Three categories of information about each **element** determine its behavior and appearance: *styles*, *attributes*, and *properties*. This how **D3** gets access to each one:

```javascript
d3.select("#someDiv").style("border", "5px darkgray dashed");
d3.select("#someDiv").attr("id", "newID");
d3.select("#someCheckbox").property("checked", true);
```

`html("content")` Gets or sets the inner HTML of selected element.

### SVG
SVG allows for simple mathematical representation of images. It provides options to draw different shapes such as Lines, Rectangles, Circles, Ellipses, etc. Hence, designing visualizations with SVG gives you more power and flexibility.

```html
<svg style="width:500px;height:500px;border:1px lightgray solid;">
</svg>
```
An `<svg>` element can be styled with CSS to have differ- ent borders and backgrounds. Or use D3 to style it! 

#### SVG: `<text>` element
svg allows for text as well as shapes. It's primarily used for **labels**.

#### SVG: `<g>` element
The `<g></g>` element doesn't exsit as a bounded space. Instead, it's used a logical grouping of elements. Let's say you want a number of shapes to be associated with each other or a shape and its label, you can place them inside a `<g>` element.

```html
<g>
<circle r="2"/>
<text>This circle’s Label</text>
</g>
```
#### transform(): An attribute of the `<g>` element
`transform` allows you to move the `<g>` element around your canvas. 
```html
<g transform="translate(100,50)">
```
The *transform* is pretty annoying because it accepts its description in the form of a text string. The line above moves the `<g>` element 100px to the right and 50px down.