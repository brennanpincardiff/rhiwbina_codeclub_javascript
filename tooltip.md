## Lesson 5 Tooltips


``` html
<!DOCTYPE html>
<head>
  <script src="https://d3js.org/d3.v4.min.js"></script>
</head>

<body>
  <div></div>
  </body>
</html>
```
### Make a circle
1. Make an SVG box in the div of a html page
2. Then add the code for a simple cirle

``` javascript
//Make an SVG box
var svgbox = d3.select("div").append("svg")
		           .attr("width", 500)
               .attr("height", 500)

 //Draw the Circle
 var circle = svgbox.append("circle")
                          .attr("cx", 30)	
                          .attr("cy", 30)	
                          .attr("r", 20)
 .style('fill', 'orange')
 .on("mouseover", function(){return tooltip.style("visibility", "visible");})
 .on("mousemove", function(){return tooltip.style("top", (event.pageY-10)+"px").style("left",(event.pageX+10)+"px");})
 .on("mouseout", function(){return tooltip.style("visibility", "hidden");});

``` 

### Add the tooltip function

``` javascript 
 var tooltip = d3.select("body")
	.append("div")
	.style("position", "absolute")
	.style("z-index", "10")
	.style("visibility", "hidden")
	.text("a simple tooltip");

 ``` 
Check out these for original code, codepen code and a more detailed example...
+ [http://bl.ocks.org/biovisualize/1016860]
+ [https://codepen.io/brennanpincardiff/pen/eXxJmp]
+ [http://bl.ocks.org/Caged/6476579]
