## What is a point cloud and its characteristics?

In our everyday world, ordinary photos are made up of many **pixels**, which form a two-dimensional grid. Each pixel is filled with RGB color values in its corresponding area, creating a complete 2D image.

**Now imagine this🤯:**

Divide the 1 × 1 × 1 meter space around you into a huge number of tiny little cubes (like slicing the entire space into millions of microscopic building blocks).  
Then apply a simple replacement rule to these small cubes:

- If a small cube contains **any part of an object** (even just a tiny bit), replace it with **a single point** at that location.
- If the small cube contains only air, leave it empty — no point is created.

Because these tiny cubes are extremely small, the continuous surface of any object gets broken down into a large number of discrete points.When these massive discrete points become a set,they can be used to represent the three-dimensional shape of an object.
As a result, the object is recorded and represented as a collection of many points distributed in three-dimensional space.

This collection of points is what we call a **point cloud**.

In short:  
**A point cloud is a set of discrete points in 3D space that together approximate the shape and surface of real-world objects.**

So the position of each points in the point cloud is described using the Cartesian coordinate system $(X,Y,Z)$,sometimes including color information $(R,G,B)$ and so on.

## Now let's start discussing the characteristics of point clouds


### 1. The disorder of point clouds
Swapping any two pixels blocks of a two-dimensional image disrupts the original ordered structure,leading to changes in semantic information,**as shown in the following [Fig1](#fig:disorder)**. 
<a id="fig:disorder">
    <div style="text-align: center;">
        ![swapping two pixels in two-dimensional photo](Fig1.jpg)
    </div>
</a>
