### Rotational Delta Robot

#### Summary / Context

Mechanical and electronic designs for a “delta” style process robot.  In particular, a “rotational delta”, which is driven by 3 pivoting upper arms.  (As opposed to a Rostock delta and similar designs where the “elbow” is mounted to a shuttle moving along a rail.)

![](http://upload.wikimedia.org/wikipedia/commons/f/f5/FANUC_M-1iA_Delta_Robot.jpg)

This repo contains my own modifications to the [FirePick Delta](http://delta.firepick.org) project.  As such, you are referred to the [FirePick repo](https://github.com/firepick-delta/firepick-delta) for the more complete project.

My primary focus here is related to pick & place.  Use care when applying these mods to other use cases.

Code here is predominantly C++ and should be easily portable.  At the moment, I’m targeting the Raspberry Pi2B platform, which is a major difference from the main project.


#### Structure

* Kinematics - Code for kinematic math, path calculations, and motor control.
* Control - Code that interfaces with the outside world - touchscreen, HTTP, etc.
* Mechanical - 3D CAD designs, CNC G-code scripts, and parts images
* Electronics - PCB designs, schematics, and Gerber files
* Documentation - Reference docs


#### Licensing

![CC-BY-SA](http://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/CC-BY-SA_icon.svg/320px-CC-BY-SA_icon.svg.png)

These files are licensed under [*Creative Commons Attribution-ShareAlike (CC BY-SA)*](https://creativecommons.org/licenses/by-sa/4.0/legalcode).  Commercial use is OK, but you are required under the license conditions to share your changes with the Internet, and also credit this author.


This license lets others remix, tweak, and build upon your work even for commercial purposes, as long as they credit you and license their new creations under the identical terms. This license is often compared to “copyleft” free and open source software licenses. All new works based on yours will carry the same license, so any derivatives will also allow commercial use. This is the license used by Wikipedia, and is recommended for materials that would benefit from incorporating content from Wikipedia and similarly licensed projects. 

[View License Deed](http://creativecommons.org/licenses/by-sa/4.0/) | [View Legal Code](https://creativecommons.org/licenses/by-sa/4.0/legalcode)

#### Maintainer

* [@Richard-Foo (Richard Hornbaker)](https://github.com/Richard-Foo)


#### A Few Words About Formats

* Mechanical design files are in Autodesk Inventor 2015 format.  A free trial is available, as is a free student license.  A free viewer may also be available.
* Electronic design files are in Eagle CAD format.  A free version is available which can view any file, but only edit smaller boards.
* *.tap files are CNC G-code files with a preamble specific to Tormach PCNC-1100
