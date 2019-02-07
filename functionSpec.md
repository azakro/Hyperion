# Hyperion Function Specifications

### GOAL
To develop a novel AR/VR interface in support efficient object manipulation,
spatial reasoning, and collaborative problem solving involved in freeform optics design.

### 3D MANIPUTLATION FUNCTIONS


```
BACSYS
```
Makes temporary backup of the lens systems, not just the lens definitions. 

```
GETGENSYSSET
```
Displays settings, specifically Strictly collinear System, Non-collinear System (explicit; dummy sfces), Non-collinear System (implicit; hidden sfces), Standard coordinate system, Canonical coordinate system.

```
INSFIEPOI
```
Adds a field point to the specified configuration.

```
INSREFLECSUR / INSREFLECSUR <c> <p> <r> <dp> <dn> [title]
```
Adds a reflective surface in the lens system. 
  - p is the index of the surface after which to insert this surface (starting from0)|
  - r is the radius of curvature
  - dp is the distance from the previous surface (surface p)
  - dn is the distance to the next surface
  - [title] is  an  optional  string  (no  spaces)

```
INSREFRACSUR / INSREFRACSUR <c> <p> <r> <dp> <dn> <g> [title]
```
Adds a refractive surface in the lens system. 
  - p is the index of the surface after which to insert this surface (starting from0)|
  - r is the radius of curvature
  - dp is the distance from the previous surface (surface p)
  - dn is the distance to the next surface
  - g is the glass code from the catalog
  - [title] is  an  optional  string  (no  spaces)
  
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
  
```
NEWSYS
``` 
Creates an empty lens system containing one configuration.
