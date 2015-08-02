### Mechanical Design Files


#### Design Logic


##### Support Frame
Design of the support frame is still TBD.

Initial idea is an open-frame design, not unlike the Tosy example shown on the main page for this project.
The idea being that an open design will eliminate collision points.
However, in practice there will be a need to adjust the head's height, attach a bed to hold the PCB, rails to mount the feeders, a conveyor belt system, etc.
There are also questions like whether the support should be floor-standing or tabletop.

I've explored using an aluminum extrusion frame (a mix of 2020 and 2040 sizes), which lends a lot of flexibility in reconfiguration;
however, while the extrusions themselves are inexpensive, the accompanying brackets and fasteners make it an expensive option.

Consideration for an open-frame design - it becomes harder to create a safety boundary for use in a public environment.
A closed-frame design can have clear enclosing panels and doors with interlocks - still very accessible, but easier to secure.

I'm not sure it makes sense to try and merge a steel frame with an extrusion frame, since it increases cost and leaves the head height inflexible.
I suspect the solution may be to mount the steel base plate at the top of an aluminum extrusion, and find ways to reduce cost of the extrusion frame.


#### A Few Words About Formats

* *.ipt files are mechanical 3D CAD designs in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* *.iam files are assemblies of individual CAD parts (or other assemblies)
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
