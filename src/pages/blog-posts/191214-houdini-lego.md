---
layout: "../../layouts/BlogLayout.astro"
title: "Houdini Lego Tool"
description: "A deep dive into creating a procedural Lego brick generator in Houdini."
date: "2019-12-14"
author: "Flore Vanackere"
thumbnail: "/images/blog-posts/191214-houdini-lego/Thumbnail.png"
---
### Introduction
Few weeks ago I made a Lego tool in Houdini. Decided to upload it here. Cheesy presentation video and piano music included.
Once you know how it works a Lego tool is something that's pretty simple to do and I recommend everyone starting out in Houdini to try it.
My tool also supports different kind of blocks as opposed to only one kind of brick that gets copied on all the points.

The cathedral model was downloaded from 3D Warehouse and made by Chris D.
![Cathedral.jpg](/images/blog-posts/191214-houdini-lego/Cathedral.jpg)
_Cathedral of Our Lady (Antwerp)_

<iframe width="800" src="https://www.youtube.com/embed/MVZZu_iCncQ?si=UiLygulu-RoN7uE_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Breakdown
The very core of this tool is only **4** nodes. Pretty simple right?

The first node creates a VDB volume from your input mesh. Next, we convert  the 3D grid of the voxels into geometry. When we have the geometry we  can extract the centre point of each little cube out of it. So now we  have 3D point cloud. The last step is to literally put any kind of mesh  you want and use the copy to points SOP.
![Annotation 2019-12-14 154938.jpg](/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20154938.jpg)

If we leave it like that the object can only be build with 1 type of Lego brick. That's why I decided to push it a little bit further (Since the first step was so difficult).
![Untitled-1.png](/images/blog-posts/191214-houdini-lego/Untitled-1.png)
## Brick Variations
This was the part I had the most trouble  with. I wanted it to support any kind of the basic Lego bricks, so doing calculations by hand seemed not like the correct approach. The solution  I came up with allows for any kind of convex shape on the X, Z axis.  Which is pretty good I think.

We start with slicing up our point cloud for every row of points
Then we go in to a nested for each loop. One will loop over the different rows and one will iterate over every point in said row.
What I do in the second loop is moving a template shape around and see where it matches the points. The matched areas get marked and will be merged together into one point. So in the example  below I'm basically looking for an area within the point cloud were a  2x4 brick would fit in.

<img src="/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20161942.jpg" width="400" alt="Shape  matching process">  

The downside is that for every shape we want to look for we have to  loop through the points. Granted only the first time will be the most  intensive loop. In my examples I searched for 2 shapes. The 4x2 and the  2x2 Lego brick. The remaining points in the end got the 1x1 brick.
I get that this might come across as a rather brute forced solution, if anyone has a better approach please let me know!
<div class="gallery-dynamic">
<img src="/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20162608.jpg" width="300" alt="Shape  matching process">
<img src="/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20163639.jpg" width="400" alt="Shape matching result">
</div>

## Brick Tool
I also made a basic brick tool that would let me generate some of the basic shaped bricks. This tool allows for 1x1, 2x3,  2x4 and 2x2 bricks. It could easily be expanded to support other types  but it wasn't really the focus of my experiment here. Albeit, it was  still fun to make.

<div class="gallery-dynamic">
    <img src="/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20164101.jpg" alt="Annotation 2019-12-14 164101" />
    <img src="/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20164729.jpg" alt="Annotation 2019-12-14 164729" />
    <img src="/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20164743.jpg" alt="Annotation 2019-12-14 164743" />
</div>

## Final

We can transfer colours by using the SOP Attribute From Map.

After all that is finished we can achieve the following results!
![Annotation 2019-12-14 165921.jpg](/images/blog-posts/191214-houdini-lego/Annotation%202019-12-14%20165921.jpg)

Here are some more example renders:
![brokentoy.jpg](/images/blog-posts/191214-houdini-lego/brokentoy.jpg)
![Car.jpg](/images/blog-posts/191214-houdini-lego/Car.jpg)
![Helmet.jpg](/images/blog-posts/191214-houdini-lego/Helmet.jpg)

I've made the .hip available on my Arstation marketplace.  
<a href="https://artstn.co/m/nOMqw" target="_blank" rel="noopener noreferrer" aria-label="Artstation marketplace link">
    <img width="250" src="/images/blog-posts/191214-houdini-lego/Cover.png" alt="thumbnail for the marketplace link" />
</a>