## Lesson 4 - Some simple code to make a map of the world
### Setup at https://codepen.io or equivalent

If necessary for the interface, add the d3 library in the Framework and Extensions and type this code into the HTML window

``` html
<head>
  <script src="https://d3js.org/d3.v4.min.js"></script>
  <script src="https://d3js.org/topojson.v2.min.js"></script>
 
</head>

<body>
  <svg width="960" height="600"></svg>
</body>
```
### Here are the steps
1. Define the variables
2. Write the function
3. Launch the function with a link to the data

#### Define the variables
``` javascript
const svg = d3.select("svg")
const myProjection = d3.geoNaturalEarth1()
const path =     d3.geoPath().projection(myProjection)
const graticule = d3.geoGraticule()
``` 

#### Write the function
The function can be shortened but...
``` javascript 
function drawMap(err, world) {
  if (err) throw err
  svg.append("path")
    .datum(graticule)
    .attr("class", "graticule")
    .attr("d", path);
  svg.append("path")
    .datum(graticule.outline)
    .attr("class", "foreground")
    .attr("d", path);
  svg.append("g")
    .selectAll("path")
    .data(topojson.feature(world, world.objects.countries).features)
    .enter().append("path")
    .attr("d", path);
}
                       
 ``` 


#### Launch the function
``` javascript 
d3.json("https://unpkg.com/world-atlas@1.1.4/world/110m.json", drawMap)  
 ``` 

### For some different styling add some CSS
Maybe try adding each part separately
``` CSS
path {
      fill: lightgray;
      stroke: #000;
    }
    .graticule {
      fill: none;
      stroke: #ccc;
      stroke-width: .5px;
    }
    .foreground {
      fill: none;
      stroke: #333;
      stroke-width: 1.5px;
    }
``` 

Code pen example [https://codepen.io/brennanpincardiff/pen/zbjZGg]

[https://medium.com/@amy.degenaro/introduction-to-digital-cartography-geojson-and-d3-js-c27f066aa84]
