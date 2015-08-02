### Mechanical Design Files

#### Structure

The following folders will appear as they have content committed:
* Arms - Upper and lower arms, including the upper arm gear
* Base - Base platform, including motor mounts and gear mounts
* Effector - Effector platforms, including head options (for now)
* Feeders - Component tape feeders
* Stand - Support stand for the base platform
* Trays - Component trays, reject tray
* Tubes - Tube feeders, vibration bed


#### Design Logic
The general design philosophy goes like this: make stationary things heavy; make moving parts light.

Why?  Because the relatively high mass of stationary components dampens movement and vibration, which makes the system more stable and maximizes accuracy.
Making the moving parts low-mass reduces their inertia / momentum so they can accelerate more rapidly with dependable accuracy.
Lower mass also means less stress on the structural components, allowing smaller arms, lighter-duty joints, and smaller motors.

Components and measurements will be metric wherever possible.
Stationary parts will be powder coated; moving parts will probably stay raw.
Screw holes and machined surfaces (e.g., bearing sockets) will be masked from paint.
Countersunk flat-head screws will be used on motor mounts; others TBD.
The variety of screw heads, sizes, and lengths will be minimized.


##### Misc Thoughts
* Need to ensure a good electrical path through all of the mechanical parts, to eliminate potential for static buildup.
	* Mask a grounding ring around non-threaded mounting bolt holes and use an internally-toothed washer under the bolt head
	* Explore whether we can source an ESD-safe acetal for the magnetic arm joints.


#### A Few Words About Formats

* *.ipt files are mechanical 3D CAD designs in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* *.iam files are assemblies of individual CAD parts (or other assemblies)
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
