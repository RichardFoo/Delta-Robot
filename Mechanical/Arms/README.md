### Mechanical Design Files


#### Variants
* Rod diameters
  * Thinner rods are cheaper and more readily available (e.g., repurposing arrow shafts from Walmart)
  * Thicker rods provide a wider cross-section for greater rigidity.  May not offer any real benefit for shorter arms - TBD.
  * Future test: Rigidity of thinner-walled large-diameter rods (e.g., 20mmx19mm), to cut weight further.
* Rod lengths
  * Initially, will match FirePick Delta's length dimension between pivot points
* Ball / socket diameter
  * FirePick Delta ships 0.375" balls with M3 studs
  * I'm using 10mm balls with M4 taps
* End taper
  * Initial design uses a 30-degree taper
  * Will also test with a 15-degree taper for more horizontal clearance


#### Design Logic


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
and also to provide instant "homing" without need for an optical limit switch.
Electronically, this feedback would need to be handled by the stepper controller for the tightest coupling.

The number of emitter / sensor pairs is TBD, as is the encoding scheme.  A study of servo encoders is planned to duplicate their schemes and benefits.


##### Gear Axles
Axles are made of H6 precision-ground stainless steel 8mm rod.
Stainless steel is used instead of carbon steel to prevent galvanic corrosion with the aluminum gear.

8mm rod is used because it matches the center diameter for the bearings being used.
Many options were considered for the axles; in the end, a straight 8mm rod was selected for several reasons:
* It allows the gear hub to directly contact the center hub of the bearing, and then to use that contact surface as a means of keeping the gear aligned axially.  This allows the assembly to avoid needing a press-fit of any parts.
* It allows the gear to be disassembled with the greatest ease, because the axle can slide out through the bearings.

The axle itself needs only to stay in the hole - its movement along the axis isn't a concern.
So, the axle only needs to be protected against falling out.
The axle could be threaded or tapped at each end for use with a fastener, but the simplest path is to drill a hole and use a retaining pin (rather than a retaining clip which requires a groove to be cut).

Open items:
* Will the retaining clip rub against stationary parts of the bearing or support?
* The 608ZZ opening is slightly larger than the 8mm rod - should we thread the rod and use a locking nut to apply pressure to sandwich the axle components together?  This would be smarter than side-loading the bearing by using it to keep the gear centered.
* Do we need a pin through the axle or a setscrew to ensure only the bearings rotate?

An alternative would have been to use a 10mm rod for the gear hub segment, and turn it down to 8mm for the bearings - this served to secure the axle without fasteners, but it meant that the axle would need to be press-fit into the gear hub, which creates problems for assembly and disassembly.


##### Gear Bearings
The bearings are type 608, the most common variety, which makes them both readily available and inexpensive.
(E.g., they're used for most skateboards.)
Enough so that it's worth designing the mechanical specs to match them.

608 bearings are 22mm diameter with an 8mm center hole and a 7mm thickness.
I'm using a 608ZZ variant, which can be found for $0.30 each.
For that price, you even get ABEC-7 tolerances, which are at the upper-end of the scale.


##### Upper Arms (Thighs)
The upper arms (also called thighs) bear both lateral and torsion loads.
Their material is still TBD, but will be either molded carbon fiber or aluminum.
They both push and pull the lower arms, plus each upper arm must be torsionally rigid to keep the effector parallel to the base via its two parallel lower arms.

Length of the upper arm is one of the most critical measurements, as it affects both the overall reach of the robot, and inversely its degree of precision.
Width of the upper arm pivots must match the effector, and wider yields greater effector stability.


##### Lower Arms (Shins)
The lower arms (also called shins) are constructed of 10mm x 8mm carbon fiber tubes.
They bear exclusively axial loads, both pushing and pulling.
Arms are coupled with magnetic joints at each end.

Longer lower arms contribute to greater distance from head to work plane, but have a very small effect on overall reach and accuracy.
Lower arms need to be at least as long as the upper arms, and all 6 lower arms must be exactly the same length.

Larger diameter arms (20mm x 18mm) have been explored because their greater cross-section yields greater stiffness.
However, they seem likely to have greater issues with collisions at each end due to the larger diameter.
This option still needs to be explored practically, as it may lead to greater accuracy at higher speeds.


##### Magnetic Joints
Arms are coupled using magnetics joints, comprised of a metal ball, a cone-shaped rod tip, and a magnet embedded inside the tip.

The balls are 10mm chrome-plated stainless spheres, tapped with M4 threads.
Balls are fixed on the effector and upper arms, with magnetic cones attached to the lower arms.

The cone tips are made from acetal (like Delrin) and milled with a matching 10mm cup and a taper to maximize the range of motion.
(If necessary, an undersized cup is better than an oversized cup, as contact with the ball is still 360˚.)
Magnets are N52 cylindrical style, 3/8" diameter by 1/4" long and rated for 12 pounds of pull.
(This application does not allow direct contact between the magnet and the sphere, so actual pull is some value less, yet multiplied by 6 rods.)

This setup appears to offer very low "stiction" or backlash without the need for lubrication.
Magnet strength can easily be increased by using longer magnets.


#### A Few Words About Formats

* *.ipt files are mechanical 3D CAD designs in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* *.iam files are assemblies of individual CAD parts (or other assemblies)
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
