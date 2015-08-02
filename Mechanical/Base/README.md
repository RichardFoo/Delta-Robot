### Mechanical Design Files


#### Design Logic
My general design philosophy goes like this: make stationary things heavy; make moving parts light.

Why?  Because the relatively high mass of stationary components dampens movement and vibration, which makes the system more stable and maximizes accuracy.
Making the moving parts low-mass reduces their inertia / momentum so they can accelerate more rapidly with accuracy.
Lower mass also means less stress on the structural components (allowing smaller arms and lighter-duty joints) and smaller motors.

Stationary parts will be powder coated; moving parts will probably stay raw.  Screw holes and machined surfaces will be masked from paint.
Countersunk flat-head screws will be used on motor mounts; others TBD.  All measurements and threads will be metric.


##### Base
The base has sub-components, including the main plate, motor mounts, and the main gear supports.

The plate itself is milled from 3/8" (9.525mm) 1018 mild steel.
Size is primarily driven by the size of the axis triangle for the main gears.
Width is added for the pass-through holes for the drive belt, and a minimum border for rigidity.

The axis triangle is desired to be as small as possible without the gears colliding with arms in certain positions.

M4 holes are drilled and tapped for mounting of standoffs for PCBs.  Holes are also milled and tapped for cable paths (TBD).

I don't foresee a cable / filament path through the center of the base, so no center hole is milled; instead, I see these paths running along the arms.
Logic here being that the effector head moves in the Z axis, so a cable routed via straight down would need to glide up and down through the hole, or potentially sag below the head and interfere with work.
Routing cables along the arms allows them to be dressed with a managed bend radius for low wear and consistent length.


Open question is how the base will be fastened to the support frame, which has not been designed yet.
Rough idea is that 2-3 10mm holes will be milled along two edges, enabling the base to be bolted to a support frame.


##### Motor Mounts
Motor mounts are milled from 1/8" (3.175mm) 1018 cold-rolled mild steel.
This thickness should be adequate for rigid motor support, particularly since the force is radial.  Since the joint will be fully welded, no supporting braces are expected to be necessary.

The motor mounts are designed to support both NEMA17 and NEMA23 mounting holes, in case a larger motor is desired.
The center hole is specifically sized for NEMA17 steppers sourced from RobotDigg.com.
For NEMA23 motors, the center hole won't be large enough, but sizing it for NEMA23 would have significantly reduced the contact surface for a NEMA17 motor, which is the primary use case.

Part of the interest in a large contact area is for heat transfer from the motor to the base plate, both for its thermal mass and also for a greater surface area for dissipation.
If this is beneficial enough, I'll plan to use thermal grease on the mounting surface to improve heat transfer.


##### Main Gear Supports
These supports are milled from 3/8" (9.525mm) 1018 cold-rolled mild steel.
Heavy thickness is used because these are the main supports for the moving parts and need to be especially rigid.
Joints will be beveled and fully welded, so no lateral stiffeners are expected to be required, given the lightness of the effector and arms.

Most of the forces will be radial, but torsional forces will also result from the arms working to keep the effector parallel as the other axes move.

Tentatively, PCBs will be mounted to the inner face of these supports, holding a matched set of light sources and sensors (probably tuned infrared).


##### Main Gears
The main gears are milled from 6061 aluminum.  Stock is purchased as discs (round bar cross-sections) minimize waste and cost.

The outer perimeter is designed as a track groove, sized to fit the width of the drive belt.
The groove has a tapered lip to keep the belt on-track.
The outer diameter is milled specifically to match the motor's drive sprocket to yield a 10:1 gear ratio.
Note that the motor drive sprocket is toothed, where the main gears are not; calculations factor this into the diameters.

The body of the gear is tapered in thickness, with a goal of minimizing mass while maintaining rigidity.
It's thinnest at the perimeter (where mass has the greatest effect on inertia), and comes to full width at the hub in the center (for rigidity at the axle).

The hub of the gear has a precision 8mm hole for the axle, and the ends of the hub are sized at precisely 10mm so they engage only with the center hub of the bearing.
The gear is held in center on the axle by the bearings which contact the hub directly.


A strong idea is to use the main gear as an encoder wheel to detect the position of the arm at any point in its path.
This idea would use a series of slots or holes at different diameters, along with an emitter and sensor mounted to the gear supports at each diameter.
These holes would have an added benefit of reducing mass for the main gear.

This would allow for immediate sensing of the arm position, first as a feedback mechanism to detect and correct for stepper slips,
and also to provide instant "homing" without need for an optical limit switch.  Electronically, this feedback would need to be handled by the stepper driver for the tightest coupling.

The number of emitter / sensor pairs is TBD, as is the encoding scheme.  A study of servo encoders is planned to duplicate their schemes and benefits.


##### Gear Axles
Axles are made of H6 precision-ground stainless steel 8mm rod.
Stainless steel is used instead of carbon steel to prevent galvanic corrosion with the aluminum gear.

8mm rod is used because this it matches the center diameter for the bearings being used.
Many options were considered for the axles.
In the end, a straight 8mm rod was selected for several reasons:
* It allows the gear hub to directly contact the center hub of the bearing, and then to use that contact surface as a means of keeping the gear aligned laterally.  This allows the assembly to avoid needing a press-fit of any parts.
* It allows the gear to be disassembled with the greatest ease, because the axle can be slid out through the bearings.

The axle itself needs only to stay in the hole - its movement along the axis isn't a concern.
So, the axle only needs to be protected against falling out.
The axle could be threaded or tapped at each end for use with a fastener, but the simplest path is to drill a hole and use a retaining pin (rather than a retaining clip which requires a groove to be cut).  Open item: will the retaining clip rub against bad parts of the bearing or support?

An alternative would have been to use a 10mm rod for the gear hub segment, and turn it down to 8mm for the bearings - this served to secure the axle without fasteners, but it meant that the axle would need to be press-fit into the gear hub, which creates problems for assembly and disassembly.


##### Gear Bearings
The bearings are of the most common variety - type 608 - which makes them both readily available and cheap.
(E.g., they're the most common type used for skateboards.)
Enough so that it's worth designing the mechanical specs to match them.

608 bearings are 22mm diameter with an 8mm center hole and a 7mm thickness.
I'm using a 608ZZ variant, which can be found for $0.30 each.
For that price, you even get ABEC-7 tolerances, which are at the upper-end of the scale.


##### Upper Arms (Thighs)
The upper arms (also called thighs) bear both lateral and torsion loads.
Their material is still TBD, but will be either molded carbon fiber or aluminum.
They both push and pull the lower arms, plus each upper arm must be torsionally rigid to keep the effector parallel to the base via its two parallel lower arms.

Length of the upper arm is one of the most critical measurements, as it affects both the overall reach of the robot, and inversely its degree of precision.


##### Lower Arms (Shins)
The lower arms (also called shins) are constructed of 10mm x 8mm carbon fiber tubes.
They bear exclusively axial loads, both pushing and pulling.
They are coupled with magnetic joints at each end.

Longer lower arms contribute to greater distance from head to work plane, but only has a very small effect on overall reach and accuracy.
Lower arms need to be at least as long as the upper arms, and all 6 lower arms must be exactly the same length.


##### Magnetic Joints
Arms are coupled using magnetics joints, comprised of a metal ball, a cone-shaped rod tip, and a magnet embedded inside the tip.
The balls are 10mm chrome-plated stainless spheres, tapped with M4 threads.
Balls are fixed on the effector and upper arms, with magnetic cones attached to the lower arms.
The cone tips are made from acetal (like Delrin) and milled with a matching 10mm cup and a taper to maximize the range of motion.
(If necessary, an undersized cup is better than an oversized cup, as contact with the ball is still 360˚.)
Magnets are N52 cylindrical style, 3/8" diameter by 1/4" long and rated for 7 pounds of pull.
(This application does not allow direct contact between the magnet and the sphere, so actual pull is some value less, yet multiplied by 6 rods.)

This setup appears to offer very low "stiction" or backlash without the need for lubrication.
Magnet strength can easily be increased by using longer magnets.


##### Effector
TBD - work in progress.  Current thinking is to use carbon fiber for the structure, shaping it as needed using a 2-part aluminum mold.
However, if it happens that a complex surface is not required, then I'll explore using PCB as the foundation, since a PCB will be needed regardless for the light ring, head connectors, etc.
Objects that may need to be supplied through the effector PCB:
* Light ring
* Camera
* Accelerometer
* Z probe
* Rotational servo
* Vacuum
* 3D printing head
* Filament feeder (for push/pull design)
* Fan
* Solder paste extruder


##### Support Frame
Design of the support frame is still TBD.

Initial idea is an open-frame design, not unlike the Tosy example shown on the main page for this project.
The idea being that an open design will eliminate collision points.
However, in practice there will be a need to adjust the head's height, attach a bed to hold the PCB, rails to mount the feeders, a conveyor belt system, etc.

I've explored using an aluminum extrusion frame (a mix of 2020 and 2040 sizes), which lends a lot of flexibility in reconfiguration;
however, while the extrusions themselves are inexpensive, the accompanying brackets and fasteners make it an expensive option.

Consideration for an open-frame design - it becomes harder to create a safety boundary for use in a public environment.
A closed-frame design can have clear enclosing panels and doors with interlocks - still very accessible, but easier to secure.

I'm not sure it makes sense to try and merge a steel frame with an extrusion frame, since it increases cost and makes the head heigh inflexible.
I suspect the solution may be to mount the steel base plate at the top of an aluminum extrusion, and find ways to reduce cost of the extrusion frame.


##### Misc Thoughts
* Need to ensure a good electrical path through all of the mechanical parts, to eliminate potential for static buildup.
	* Mask a grounding ring around non-threaded mounting bolt holes and use an internally-toothed washer under the bolt head
	* Explore whether we can source an ESD-safe acetal for the magnetic arm joints.


#### A Few Words About Formats

* *.ipt files are mechanical 3D CAD designs in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* *.iam files are assemblies of individual CAD parts (or other assemblies)
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
