# What is a point cloud and its characteristics?

In our everyday world, ordinary photos are made up of many **pixels**, which form a two-dimensional grid. Each pixel is filled with RGB color values in its corresponding area, creating a complete 2D image.

<br><br>

## **Now imagine this🤯:**

Divide the 1 × 1 × 1 meter space around you into a huge number of tiny little cubes (like slicing the entire space into millions of microscopic building blocks).  

Then apply a simple replacement rule to these small cubes:

- If a small cube contains **any part of an object** (even just a tiny bit), replace it with **a single point** at that location.
- If the small cube contains only air, leave it empty — no point is created.

Because these tiny cubes are extremely small, the continuous surface of any object gets broken down into a large number of discrete points. When these massive discrete points become a set, they can be used to represent the three-dimensional shape of an object.  
As a result, the object is recorded and represented as a collection of many points distributed in three-dimensional space.

This collection of points is what we call a **point cloud**.

<br>

## In short  
**A point cloud is a set of discrete points in 3D space that together approximate the shape and surface of real-world objects.**

So the position of each point in the point cloud is described using the Cartesian coordinate system $(X,Y,Z)$, sometimes including color information $(R,G,B)$ and so on.

<br><hr style="border: 1px solid #ddd; margin: 2em 0;">

## Now let's start discussing the characteristics of point clouds

### 1. The disorder of point clouds

Swapping any two pixels blocks of a two-dimensional image disrupts the original ordered structure, leading to changes in semantic information as shown in the following **[Fig. 1](#fig:disorder)** and **[Fig. 2](#fig:disord2)**.

<div style="text-align: center; margin: 2em 0;">
  <table border="0" style="width: 100%; max-width: 900px; margin: 0 auto;">
    <tr>
      <td style="text-align: center; padding: 10px;">
        <a id="fig:disorder"></a>
        <img src="Image/Fig1.jpg" alt="Fig 1" style="max-width: 100%; height: auto; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        <br><br>
        <strong>Fig. 1.</strong> Original ordered structure
      </td>
      <td style="text-align: center; padding: 10px;">
        <a id="fig:disord2"></a>
        <img src="Image/Fig2.jpg" alt="Fig 2" style="max-width: 100%; height: auto; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        <br><br>
        <strong>Fig. 2.</strong> Disordered after swapping
      </td>
    </tr>
  </table>
</div>

However, when you exchange the two points "A" and "B" in the point cloud, you will be surprised to find that the shape of point cloud and its semantics have not changed (Only considering that the points only contain coordinate information), which is completely different from the picture.

If you randomly select two points in **[Fig. 3](#fig:pointcloud)** and swap them, nothing will happen and everything will remain the same: the ground is still the ground, the table is still the table.

<div style="text-align: center; margin: 2em 0;">
  <img src="Image/Fig3.jpg" alt="Fig 3" style="max-width: 80%; height: auto; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
  <br><br>
  <strong>Fig. 3.</strong> Point cloud dataset
</div>

<br><hr style="border: 1px solid #eee; margin: 3em 0;">

### 2. The non-uniformity of point clouds

It's easy to understand that in the process of collecting data, objects closer to the sensor have a higher point cloud density, while objects farther away have a lower point cloud density. Moreover, due to the fact that mainstream collection techniques are based on light reflection, there are no points other than the surface of the object.

**It should be noted that sensors can only see the side of the object facing them, and in a single data acquisition, the back and interior of the object are completely "vacuum zone".**

<div style="text-align: center; margin: 2em 0;">
  <table border="0" style="width: 100%; max-width: 900px; margin: 0 auto;">
    <tr>
      <td style="text-align: center; padding: 10px;">
        <a id="fig:visible"></a>
        <img src="Image/Fig4.jpg" alt="Fig 4" style="max-width: 100%; height: auto; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        <br><br>
        <strong>Fig. 4.</strong> The side facing sensors
      </td>
      <td style="text-align: center; padding: 10px;">
        <a id="fig:vacuum"></a>
        <img src="Image/Fig5.jpg" alt="Fig 5" style="max-width: 100%; height: auto; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        <br><br>
        <strong>Fig. 5.</strong> The side not facing the sensor have a "vacuum zone"
      </td>
    </tr>
  </table>
</div>

<br><hr style="border: 1px solid #eee; margin: 3em 0;">

### 3. Rotation and translation invariance

When you rotate or translate a point cloud, the coordinates of points will change, but the category and properties of the object will not change.

<br><hr style="border: 1px solid #eee; margin: 3em 0;">

### 4. Contains multiple attributes

In public datasets, you usually see some colored point clouds because in basic $(X,Y,Z)$, point cloud can also carry other related information, such as intensity, color, normal vectors, etc. The introduction of these additional information also expands the methods of subsequent point cloud processing.

<div style="text-align: center; margin: 2em 0;">
  <img src="Image/Fig6.jpg" alt="Fig 6" style="max-width: 80%; height: auto; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
  <br><br>
  <strong>Fig. 6.</strong> Point cloud with color
</div>

<br><hr style="border: 2px solid #4a90e2; margin: 4em 0;">

### Next steps

At this point, everyone already knows the basic characteristics of point clouds.  

In the next chapter, I will explain the I/O operations of point clouds **<ins>(which are actually available in the Open3D document library)</ins>**.

<div style="text-align: center; margin: 3em 0;">
  <a href="https://www.open3d.org/docs/release/" target="_blank" style="background-color: #4a90e2; color: white; padding: 14px 28px; text-decoration: none; border-radius: 8px; font-size: 1.1em; font-weight: bold; box-shadow: 0 4px 12px rgba(74,144,226,0.3);">
    📚 Open3D Official Documentation
  </a>
</div>