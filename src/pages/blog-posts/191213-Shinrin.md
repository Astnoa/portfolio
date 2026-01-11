---
layout: "../../layouts/BlogLayout.astro"
title: "Shinrin: Tactical Turn Based Combat"
description: "Exploring pathfinding and tactical combat systems in an Unreal Engine 4 prototype project."
date: "2019-12-13"
author: "Flore Vanackere"
thumbnail: "/images/blog-posts/191213-shinrin/035.jpg"
---
### Overview
I decided to do a little write-up on this project because even though it has been dormant for the last few years, it's still an interesting showcase of my experience with UE4 Blueprints and C++.

Everyone has these passion projects, Project _Shinrin_ is mine. It's supposed to be a tactical turn based rpg with a _Total war_-like world map and _XCOM_-like combat. But we're not here to talk about game design.

If you want the tl;dr version, this video below was the last one I uploaded. It showcased how my system was relatively well implemented since I could make two AI teams battle each other without much alteration in the code.

<iframe width="800" src="https://www.youtube.com/embed/eG69hdxOhXQ?si=feVew35m-hXtBajO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Here is the playlist with all the videos I uploaded:
https://www.youtube.com/playlist?list=PLGAKcxMWqHiE4mDnQ9Hyv7N7h15q3t4Ho
  
### Development
When I started out I researched different pathfinding techniques like A* or Dijkstra. Which was very interesting and I remember having a lot of fun with these. I made everything in blueprints at this point.
<img src="/images/blog-posts/191213-shinrin/006.jpg" width="400" alt="A* pathfinding">  
I just added and changed stuff as I liked without really focusing on getting a prototype completed. Like for example a map editor. Which was totally not needed at this point. But the idea intrigued me.(See playlist)
![map editor](/images/blog-posts/191213-shinrin/026.gif)  
After I began to run into performance issues I started to rewrite almost everything from scratch and the interesting part is that I moved all my base classes and the more heavier functions (like pathfinding) to **C++**. Which was a huge performance help. This was also the first time I used C++ in Unreal Engine.

Ultimately, the obstacle that made me stop working on it was a good Ability framework. While most things worked okay-ish, the one part that was still very ugly coded was the combat/action phase. I was trying to find a way to create a solid framework for it, so I didn't have to rewrite everything 5 times. In the end I never got this to work and I think I also managed to break some stuff after trying to implement Unreal's own Abilities system in my project.

<img src="/images/blog-posts/191213-shinrin/035.jpg" alt="Screenshot">

I hope I can work on this or something similar again in the future. But, needless to say this was a very fun project and I had gained a wealth of knowledge while working on it.