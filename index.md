# Research Journal Blog

<br>

## Friday March 1st, 2019
This week, Sydney and I did some research and implementation with Vuforia in Unity. With our goal of having a tactile user interaface in Hyperion, we are planning on using the image tracking library in Vuforia in order to implement marker based tracking in Hyperion. 

We started with testing this image and its tracking in the Unity game test:

![UofR](1.png =100x100)

After downloading Vuforia, configuring Unity to support Vuforia, adding this image to the Image Target database on my personal Vuforia developers account online, and finally exporting this library into Unity, we were able to get the image with its tracking capabilities into Unity.

This also allowed for a 3D object to be placed on the image in Unity, which would show up in testing when holding up the specific printed image on camera. 

## Friday February 22nd, 2019

This week I've reviewed the CHI 2018 Best Paper Award, 'Pinpointing: Precise Head- and Eye-Based Target
Selection for Augmented Reality'. 

The paper summarizes some 'requirements' for pinpointing interactions-- 
> 1) "Pinpointing must balance the needs of selecting large
objects with minimal speed and effort, with the ability
to select very small targets when desired."

> 2) "Because wearable AR platforms overlay content
directly on the real world, interaction should leverage
the context provided by a user’s visual focus."

> 3) "To afford mobility in interactive environments and
provide a natural experience with virtual content, use
of wieldy, external devices should be minimized."

> 4) "Interaction in AR applications should be as ‘invisible’
as possible, so that users are primarily focused on real
and virtual objects, and not mechanics of the interface."

> 5) "Interactions that trigger noticeable object behaviours
should be deliberate, so that users are not distracted by
unintended consequences of actions."

##### Some other major points:
- control through eye gaze can be confusing, tiring, and has a steeper learning curve for the user compared to hand-pointing, even if the input was faster
- head-pointing provides good hands free interactions, but in terms of usabillity it still isn't as good as hand-based input because of lower muscle fatigue
- eye-gaze as an input, even with its tracking limitations, could become more accurate if coupled with hand gestures or handheld devices

## Friday February 15th, 2019

This week I've reviewed two papers:
- The Neural Bases of the Egocentric and Allocentric Spatial Frame of Reference, Zaehle et al., 2007
- Manipulation of 3D Objects in Immersive Virutal Environments, Mendes et al., 2016

##### The Neural Bases of the Egocentric and Allocentric Spatial Frame of Reference
This artical discusses the effect that spacial movements have on the brain, and what part of the brain. Frame of Reference (FoR) is important to distinguish in an application - whether it be egocentric, where the objects in a space are represented in reference to oneself, or allocentric, where the objects in a space are represented independent of onself and in reference to each other. Based on how these environments are set up, neuronal circuits in spacial cognition are affected. The study described used "verbal descriptions of spatial relations", either in repect to the listener for egocentric testing, or without reference to the listener for allocentric testing, in order to see the areas of the brain affected. 

>"By using exclusively verbal descriptions we provide strong evidence that spatial processing requires primary visual cortex functions, which reflect mental imagery processing. The results of this study show that egocentric and allocentric spatial coding are partly unique domains which recruit distinct brain regions"

In building the Hyperion application on a new platform it is important to consider chosing the right frame of reference, either egocentric or allocentric, because of how differently they affect the user's congnition. 

##### Manipulation of 3D Objects in Immersive Virutal Environments
Mendes overviews the state-of-the-art 3D object manipulation technology in virtual environments. 

> "Knowing the user's head position, it is possivle to generate a visualization frustum to each eye to create the illusion of virtual objects being part of the physical world. This illusion is even stronger when users are allowed to freely move their heads and see different sides of a virtual object in their own perspective, without the need to manipulate cameras or widgets." 

The article gives a taxonomy of virtual environments, where the display is split between perceived space, actual space, and viewpoint correlation, including both 2D and 3D constraints. With this comes 3D object manipulation that is split into "three parts: selection, spatial transformation, and release," which can be even further "divided into translation, rotation and scale". Transformations require calculations of three axis, or degrees of freedom (x, y, z). 

These specifications are applied to "mid-air maipulations (using 2D displays, either with 2D or 3D perceived space, and a 3D input space)," like HoloLens. In comparing this platform with a "6DOF Hand, which uses the dominant hand to grab, move and rotate objects, and the distance between both hands for scale" and a "3DOF Hand, in which the dominant hand only moves the object, while rotation and scale are given by the non-dominant hand"

> "User evalution results suggest that mid-air interactions are better than touch based, and 6DOF Hand and Handle-bar are both faster and preferred by participants"

This information can be applied to the Hyperion project in making decisions on the hand manipulation capabilities in the 3D HoloLens environment. 


## Friday February 8th, 2019

This week I worked on creating the function specifications, specifically for functions that would be useful in 3D interactions. Functions like selection, translation, rotation, and scaling are important to locate in the backend in order to find what is needed for manipulation in the front end. 

##### Important 3D Manpulation Functions: 

```
SURMOV
``` 
Moves (displaces, decenters) one or more surfaces

```
SURTIL / SURTIL <c> <n> <a> <p> <axis>
``` 
Tilts (rotates) one or more surfaces.
  - c is the configuration number (starting from 0)
  - n is the index of the surface to tilt
  - a is the tilt angle in degrees
  - p is the distance from surface n to the pivot axis
  - axis is one of “x,” “y,” or “z,” the pivot axis

