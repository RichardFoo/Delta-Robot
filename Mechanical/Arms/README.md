### Mechanical Design Files

This is the lower arm (aka shin) for a rotary delta design.
Shaft is carbon fiber for rigidity and low mass.
Ends are machined Delrin / acetal for smoothness, low friction, and lack of magnetic properties.
Design uses magnetically-coupled ball joints for virtually zero backlash.

Chrome-plated steel balls are held in place by magnets inserted in the rear of the rod end.
The socket is milled with a 0.1mm spacing between the ball and magnet to prevent friction wear.
Magnets are cylindrical N52, 0.375" diameter, 0.25" long, rated for 12 pounds of pull.

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


##### Upper Arms (Thighs)
The upper arms (also called thighs) bear both lateral and torsion loads.
Their material is still TBD, but will be either molded carbon fiber or aluminum.
They both push and pull the lower arms, plus each upper arm must be torsionally rigid to keep the effector parallel to the base via its two parallel lower arms.

Length of the upper arm is one of the most critical measurements, as it affects both the overall reach of the robot, and inversely its degree of precision.
Width of the upper arm pivots must match the effector, and wider yields greater effector stability.


##### Lower Arms (Shins)
The lower arms (also called shins) are constructed of 10mm x 8mm carbon fiber tubes.
They bear exclusively axial loads, both pushing and pulling.
They are coupled with magnetic joints at each end.

Longer lower arms contribute to greater distance from head to work plane, but have a very small effect on overall reach and accuracy.
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


#### A Few Words About Formats

* *.ipt files are mechanical 3D CAD designs in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* *.iam files are assemblies of individual CAD parts (or other assemblies)
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
