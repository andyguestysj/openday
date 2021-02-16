---
title: Terrain Generation
permalink: /docs/2-terrain-1/
---

## Noise/Height Map Based Generation

There are numerous approached to terrain generation. The most common involve raising points on a grid through a semi-random process to generate a height map that simulates somewhat realistic terrain. Obviously the heights on the map cannot be purely randomly generated, that would generate a spiky mess. What is needed is something that is based on randomness (so different terrains can be generated) but which gives some form of structure to the map.  

### Noise Height Map

A height map can be presented as a 2D image where the colour at each point represents the height of that point. Black represents the lowest point, white the highest, with the shades of grey showing the heights in between.  

<img src="{{ "/assets/img/terrain/noise.png" | relative_url }}" alt="noise map" class="img-responsive">

These heights can be used to draw a terrain by translating the X, Y of the image to the X, Z of a 2d plane in 3D space and using the colour to determine the Y position (height) of each point in the grid.  

<img src="{{ "/assets/img/terrain/2dgrid.png" | relative_url }}" alt="noise map" class="img-responsive">  

This can be be drawn as quads (four corners) or triangles. Triangles are more useful in computer graphics since they are guaranteed to be planar.  

## Algorithmic Height Map Generation

There are a number of algorithms for generating height maps. A few are described below

### Midpoint Displacement

The easiest method is midpoint displacement.

**2D Midpoint Displacement**

It is simple to demonstrate midpoint displacement in two dimensions.

Start with two points and a line connecting them. The points should be at x = min and x = max with the y values assigned randomly.  

Find the mid point of the line (x3,y3) at ((x1 + x2)/2, (y1+y2)/2) and randomly raise or lower the y value of the midpoint by a random amount proportional to the length of the line.  

<img src="{{ "/assets/img/terrain/mid2d1.png" | relative_url }}" alt="mid point displacement" class="img-responsive">   

Then repeat the process for the two lines you now have, (x1,y1) to (x3, y3) and (x3, y3) to (x2, y2).  

<img src="{{ "/assets/img/terrain/mid2d2.png" | relative_url }}" alt="mid point displacement" class="img-responsive">   

Keep repeating this process.  

<img src="{{ "/assets/img/terrain/mid2d3.png" | relative_url }}" alt="mid point displacement" class="img-responsive">   

The line gradually looks more like realistic terrain.  

<img src="{{ "/assets/img/terrain/mid2d.gif" | relative_url }}" alt="mid point displacement" class="img-responsive">   

**3D Midpoint Displacement**

3D midpoint displacement is more involved but basically the same process.  

* Start with four corners at the extremes of x and z. 
* Randomly assign a height (y-value) to each point
* Find the midpoint of each side of the square formed by the three points
* Set the height of each midpoint to the average of the ends plus a small random variance
* Calculate the midpoint of the square from the average of the midpoints calculated in the last two steps and add a small variance in height
* Recursively repeat the process for the four new, smaller squares you've just created.

<img src="{{ "/assets/img/terrain/mid3d.png" | relative_url }}" alt="mid point displacement" class="img-responsive">   

*Limitations* 
The grid has to have a final dimensions of (2 to the power of n)+1 to be able to keep finding midpoints.  
The outcome looks somewhat unnatural and tends to have a direction to it.  

#### Diamond Square

To overcome the "direction" limitation of the midpoint displacement approach, the diamond square approach is often used.  

<img src="{{ "/assets/img/terrain/diamond.png" | relative_url }}" alt="Diamond Square" class="img-responsive"> 

In this approach the midpoint is alternately calculated from the surrounding square and diamond as shown above.  

### Noise

#### Value Noise

[https://en.wikipedia.org/wiki/Value_noise](https://en.wikipedia.org/wiki/Value_noise)  

#### Perlin Noise

[https://en.wikipedia.org/wiki/Perlin_noise](https://en.wikipedia.org/wiki/Perlin_noise)    

#### Simple Noise

[https://en.wikipedia.org/wiki/Simplex_noise](https://en.wikipedia.org/wiki/Simplex_noise)

#### Vorley Noise

[https://en.wikipedia.org/wiki/Worley_noise](https://en.wikipedia.org/wiki/Worley_noise)  







## More Links

Introduction on Medium.com [https://medium.com/@miguelceledon/exploring-the-game-development-world-procedural-terrain-generation-theory-849d6e54f3a1](https://medium.com/@miguelceledon/exploring-the-game-development-world-procedural-terrain-generation-theory-849d6e54f3a1)  

[https://davidjorna.com/Terrain1.html](https://davidjorna.com/Terrain1.html)  

[Wikipedia - Fractal Landscapes](https://en.wikipedia.org/wiki/Fractal_landscape)  

## Papers

*Algorithms and Approaches For Procedural Terrain Generation* Rose, T. Bakaoukas, A. 
*Procedurally Generating Terrain* Archer, T.
[A Survey of Procedural Terrain Generation using Evolutionary Algorithms](https://titan.csit.rmit.edu.au/~e46507/publications/ptg-raffe-cec2012.PDF)  

## Module Content

[https://www.cs.umd.edu/class/spring2019/cmsc425/lectures.shtml](https://www.cs.umd.edu/class/spring2019/cmsc425/lectures.shtml)  - Perlin Noise Lectures  
(Lots of other good stuff here too)  

Techniques for Fractal Terrain Generation [https://web.williams.edu/Mathematics/sjmiller/public_html/hudson/Dickerson_Terrain.pdf](https://web.williams.edu/Mathematics/sjmiller/public_html/hudson/Dickerson_Terrain.pdf)   




