## Lesson 3
### Setup at [jsfiddle.net](https://jsfiddle.net/).

Add the d3 library in the Framework and Extensions and type this code into the HTML window

``` html
<div></div>
```
### Make circles
1. Make an SVG box in the div of a html page
2. Add the data for the circles
3. Create drag - for dragging the circles
4. Code attributes and draw circles

``` javascript
// make a Class
var activeClassName = 'active-d3-item';

//Make an SVG box
var svg = d3.select('body').append('svg').attr('width', 960).attr('height', 500);

// draw two circles from data
//The data for two circles
var data = [
  { 'x': 30, 'y': 30 },
  { 'x': 100, 'y': 100 }
];

// this code allows the dragging 
// it calls functions called dragstarted, dragged and dragended
var drag = d3.behavior.drag()
    .origin(function(d) { return d; })
    .on('dragstart', dragstarted)
    .on('drag', dragged)
    .on('dragend', dragended);

// Generating the svg circle attributes
var attributtes = {
    'r': 20,
    'cx': function(d) {
        return d.x;
    },
    'cy': function(d) {
        return d.y;
    }
};

svg
  .selectAll('circle')
      .data(data)
  .enter()
      .append('circle')
          .attr(attributtes)
          .call(drag);
``` 

### This is the code for the functions

``` javascript 
  
function dragstarted() {
    d3.select(this).classed(activeClassName, true);
}
function dragged(d, i) {
    var circle = d3.select(this);
    
    // Update the marker properties
    circle
        .attr('cx', d.x = d3.event.x)
        .attr('cy', d.y = d3.event.y);
}
function dragended() {
    d3.select(this).classed(activeClassName, false);
}                            
 ``` 

### For some different styling add some CSS
``` CSS
circle {
    shape-rendering: crispEdges;
    vector-effect: non-scaling-stroke;
    fill: lightsteelblue;
    stroke: steelblue;
    stroke-width: 1.5px;
}
circle:hover {
    fill: red;
    cursor: pointer;
}
circle.active-d3-item {
    fill: red;
}
``` 

[Code in jsfiddle](https://jsfiddle.net/brennanpincardiff/e5pcruhn/14/)
Resource: (https://bl.ocks.org/dimitardanailov/49f07bea0ed8adc92daee2162ac87c6c)
