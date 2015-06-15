### Mechanical Design Files

This is the lower arm (aka shin) for a rotary delta design.
Shaft is carbon fiber for rigidity and low mass.
Ends are machined Delrin / acetal for smoothness, low friction, and lack of magnetic properties.

Ball joints are magnetically coupled with magnets placed inside the rear of the rod end.
The socket is milled with a 0.1mm spacing between the ball and magnet to prevent friction wear.
Magnets are cylindrical N52, 0.375" diameter, 0.25" long, rated for 12 pounds of pull.

#### Variants
* Rod diameters
  * Thinner rods are cheaper and more readily available (e.g., repurposing arrow shafts form Walmart)
  * Thicker for wider cross-section / greater rigidity.  May not offer any real benefit for shorter arms
* Rod lengths
  * Initially, will match FirePick Delta's length dimension between pivot points
* Ball / socket diameter
  * FirePick Delta ships 0.375" balls with M3 studs
  * I'm using 10mm balls with M4 taps
* End taper
  * Initial design uses a 30-degree taper
  * Will also test with a 15-degree taper for more horizontal clearance

#### A Few Words About Formats

* *.ipt files are mechanical 3D CAD designs in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* *.iam files are assemblies of individual CAD parts (or other assemblies)
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
