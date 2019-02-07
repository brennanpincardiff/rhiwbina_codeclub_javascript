### Setup
Go to [jsfiddle.net](https://jsfiddle.net/).

You will need add the d3 library in the Framework and Extensions

Type this code into the HTML window

``` html
<div>

</div>
```

### Make a circle
1. Make an SVG box in the div of a html page
2. Then add the code for a simple cirle

``` javascript
//Make an SVG box
var svgbox = d3.select("div").append("svg")
		             .attr("width", 500)	// gives size in pixels of svg box
                             .attr("height", 500)

 //Draw the Circle
 var circle = svgbox.append("circle")
                          .attr("cx", 30)	// x position of circle
                          .attr("cy", 30)	// y position of circle
                          .attr("r", 20);	// radius of circle (controls size)
``` 

3. Then make some other shapes

``` javascript 
 //Draw an orange Rectangle
 var rectangle = svgbox.append("rect")
                             .attr("x", 100)	       // x position of top left of rectangle
                             .attr("y", 100)	       // y position of top left of rectangle
                            .attr("width", 50)	       // width of rectangle in pixels
                            .attr("height", 100)       
                            .style('fill', 'orange');  // fill and colour
                            
                      
 // control colour with rgb 
 var rectangle = svgbox.append("rect")
                             .attr("x", 100)
                             .attr("y", 200)
                            .attr("width", 50)
                            .attr("height", 100)
                            .style('fill', 'rgb(255,0,255)'); 	// how much red, green and blue - play and learn
  
  
  
 // draw multiple circles in a loop                               
var i;			// declare a variable
for (i = 0; i < 4; i++) { 		//  start of loop
  //Draw 4 Circles
  var circle = svgbox.append("circle")
                          .attr("cx", 30 + i*50)
                          .attr("cy", 400)
                          .attr("r", 20);
}    // end of loop
```	

This code is [here](https://jsfiddle.net/brennanpincardiff/n75wrkua/15/)
