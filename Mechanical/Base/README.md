### Mechanical Design Files


#### Design Logic

##### Base
The base has sub-components, including the main plate, motor mounts, and the main gear supports.

The base plate is milled from 3/8" (9.525mm) 1018 mild steel.
Circumference of the base is primarily driven by the size of the axis triangle for the main gears.
Width is added for the pass-through holes for the drive belt, and a minimum border for rigidity.

The axis triangle is desired to be as small as possible without the gears colliding when arms are in certain positions.

M4 holes are drilled and tapped for mounting of standoffs for PCBs.  Holes are also milled and tapped for cable paths (TBD).

I don't foresee a cable / filament path through the center of the base, so no center hole is milled; instead, I see these paths running along the arms.
Logic here being that the effector head moves in the Z axis, so a cable routed via straight down would need to glide up and down through the hole, or potentially sag below the head and interfere with work.
Routing cables along the arms allows them to be dressed with a managed bend radius for low wear and consistent length.


Open question is how the base will be fastened to the support frame, which has not been designed yet.
Rough idea is that 2-3 10mm holes will be milled along two edges, enabling the base to be bolted to a support frame.
If an extruded aluminum frame is used, then M5 bolts will likely be used instead (since they're the thread of choice with 2020 extrusions).


##### Motor Mounts
Motor mounts are milled from 1/8" (3.175mm) 1018 cold-rolled mild steel.
This thickness should be adequate for rigid motor support, particularly since the force is purely radial.
Since the joint will be fully welded, no supporting braces are expected to be necessary.

The motor mounts are designed to support both NEMA17 and NEMA23 mounting holes, in case a larger motor becomes necessary.
The center hole is specifically sized for NEMA17 steppers sourced from RobotDigg.com.
For NEMA23 motors, the center hole won't be large enough, but sizing it for NEMA23 would have significantly reduced the contact surface for a NEMA17 motor, which is the primary use case.

Part of the interest in a large contact surface is for heat transfer from the motor to the base plate, both for its thermal mass and also a greater surface area for heat dissipation.
If this is beneficial enough, I'll plan to use thermal grease on the mounting surface to improve heat transfer.


##### Main Gear Supports
These supports are milled from 3/8" (9.525mm) 1018 cold-rolled mild steel.
Heavy thickness is used because these are the main supports for the moving parts and need to be especially rigid.
Joints will be beveled and fully welded, so no lateral stiffeners are expected to be required, given the lightness of the effector and arms.

Most of the forces will be radial, but torsional forces will also result from the arms working to keep the effector parallel as the other axes move.

Tentatively, PCBs will be mounted to the inner face of these supports, holding a matched set of emitters and sensors to detect gear angle.


#### A Few Words About Formats

* *.ipt files are mechanical 3D CAD designs in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* *.iam files are assemblies of individual CAD parts (or other assemblies)
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
