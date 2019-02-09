## Lesson 2
### Setup at [jsfiddle.net](https://jsfiddle.net/).

Add the d3 library in the Framework and Extensions and type this code into the HTML window

``` html
<div></div>
```
### Make a circle
1. Make an SVG box in the div of a html page
2. Then add the code for a simple cirle

``` javascript
//Make an SVG box
var svgbox = d3.select("div").append("svg")
		             .attr("width", 600)	// gives size in pixels of svg box
                             .attr("height", 600)

 //Draw a Circle
 var circle = svgbox.append("circle")
                          .attr("cx", 30)	// x position of circle
                          .attr("cy", 30)	// y position of circle
                          .attr("r", 20);	// radius of circle (controls size)
                          .style("fill","blue")
``` 
### Add some movement using the transition

``` javascript

circle  // wait 1 second, then move circle to another location
	.transition()  // This function tells us to change the circle
	.duration(3000)    // how long the change will take
	.delay(1000)       // wait for a second
	.attr("cx",600)    // move to this x location
	.attr("cy",150)    // move to this y location

``` 
### Change colour

``` javascript

// add this to the circle object
	.attr("r",50);

``` 
### Change size
``` javascript

// add this to the circle object
	.attr("r",50);
``` 

Hat tip: (https://bl.ocks.org/galkamax/c19642317ac807fe13a99bbcf2eaaa75)
