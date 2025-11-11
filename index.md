---
layout: content
---


<h1> About </h1>

<span style="color: #828282; font-size: 17px;"> 
 In my free time I do programming - mainly projects that I could use to fill my portfolio.
 I'm quite familiar with C++, C, Unity Game Engine, C# and Python. On this portfolio site I put all of my interesting projects. I study computer science in the Silesian University of Technology. I am currently researching second and third level programming.
 Check out my projects <a href=" {{ '/work/' | relative_url }} " style="font-weight: bold;"> here!</a>
 </span>

# Latest project:

# N-Body Gravitational Modeler

This project is a high-performance, interactive prototype built in Unity that simulates the gravitational dynamics of an N-body system.

# The Core Idea

The "N-body problem" is a classic computational challenge: how do you simulate the motion of $N$ (e.g., 100,000) particles that are all gravitationally attracting each other?

A simple, "brute-force" approach, where every particle calculates the force from every other particle, is an O(n^2) algorithm. This means for 100,000 bodies, you would need 100,000 times 100,000 = 10,000,000,000 (ten billion) calculations per frame, making real-time simulation impossible.

This prototype solves this performance barrier by implementing a dual optimization strategy:

1.  **Algorithmic Optimization:** It uses the **Barnes-Hut algorithm**, an O(n \log n) approximation that intelligently groups distant particles into clusters, drastically reducing the number of calculations.
    
2.  **Hardware Optimization:** It leverages Unity's **Data-Oriented Technology Stack (DOTS)**, specifically the **C# Job System** and **Burst Compiler**, to execute all simulation logic in parallel across all available CPU cores.
    

The result is a fully custom physics sandbox, running its own simulation logic completely independent of Unity's built-in 3D physics engine. It is capable of handling hundreds of thousands of bodies in real-time while providing a full UI to control the simulation's physical parameters.


### Screenshots

![Screenshot]({{ site.baseurl }}images/nbody/1.png)

![Screenshot]({{ site.baseurl }}images/nbody/3.png)


