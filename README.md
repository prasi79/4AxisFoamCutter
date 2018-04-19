# 4AxisFoamCutter

We wanted to build an UAV out of foam, since there will be many iterations of designs to get through before reaching our goal. We decided to make a device to help us get through the iterations an bit faster, A hot wire cutter is the most efficient and clean way to cut foam. A CNC hot wire cutter is even better! It is an awesome tool to have when you are building airplanes out of foam. A properlly configured machine can save you a lot of time and produce a buttery smooth cut.

Mechanically, its not complicated to make a CNC Hot wire cutter. All you need is 4 independed linear axes, two horizontal axes and two vertical axes stacked on top of it. This can be acheived by any means such as linear bearings, smooth rods and also drawer slides. The axes are driven by stepper motors. There are minimal cutting forces involved, the machine only needs to be rigid enough to witstand the tension of the wire streched between the towers.

The problem is how to control 4 independent axes at the same time. Most tutorials online are for 3-axis 3D printers. Then there are documentation on people using expensive software and difficult to find hardware for making their 4-axis foam cutter.There does not seem to be enough documentation on building a 4-axis machine using easily available parts such as parts from a 3D printer kit and open source sotware. We found some people who had done similar projects and decided to make a CNC hot wire cutter ourselves and try it out.

## Hot wire CNC Resources

[Hot wire cutter, RcKeith](http://www.rckeith.co.uk/cnc-hot-wire-foam-cutter/)  
[4-axis cnc hotwire cutter (arduino+Ramps)](https://www.rcgroups.com/forums/showthread.php?2915801-4-Axis-Hot-Wire-CNC-%28Arduino-Ramps1-4%29-Complete-Solution)  
[WingGcode](https://github.com/swarfer/winggcode)  
[Free CNC Software](http://www.rckeith.co.uk/free-cnc-software-3-and-4-axis/)  
[4-axis Arduino based Hot wire cutter](https://www.rcgroups.com/forums/showthread.php?2388809-4-axis-Arduino-based-CNC-hot-wire-foam-cutter)  
[Devcnc Foam cutting software](http://www.devcad.com/eng/devcncfoam_f1_3.asp)  
[Jedicut foam cutting software](https://www.jedicut.com/)  
[Arduino Uno based foam cutter](https://sites.google.com/site/foamcuttercnc/software)  
[Nichrome wire Application Calculator](http://www.jacobs-online.biz/nichrome/NichromeCalc.html)  
[G-codes simply explained](https://all3dp.com/g-code-tutorial-3d-printer-gcode-commands/)


## Hardware

1. Plywood (12mm)
2. Rails (Steel tubes, Smooth rods)
3. Stepper Motors (one for each axis)
4. Lead screw (M8 x 600mm, as long as you need the axis to be)
5. Ramps 1.4
6. A4988 Stepper driver (one for each axis)
7. Arduino Mega 2560
8. Nichrome wire (30 guage for smaller builds and 26 guage for larger ones)

## Software

1. Grbl Hotwire Controller   
2. 4-Axis G-code Generator  
    1. Wing Gcode  
    2. Jedicut  
    3. FoamXL  
 
## Building the Machine

We realized that the most difficult part of making a CNC hot wire cutter was the G-code and Controlling systems. So we decided to start from there. In our inital research we found many people using DevFoam and profilli for generating the G-code and using Mach3 to control their machine. But unfortunately, these softwares were not free and to run a Mach3 machine you need a parallel port, which is outdated now. Then our search lead to an Arduino based 4-axis cutter developed by [Marginally clever](https://www.marginallyclever.com/) which used an arduino Mega2560 and the Ramps 1.4 CNC sheild.

His page has codes for moving 4 independent axis and a Java based G-code sender application that could send the the G-code secquentially to the Arduino using the serial port. We tried this solution and after some fiddiling around, we got it working. Not the easiest or most straight forward method. There is almost not documentation on how to use it.

[RcKeith](http://www.rckeith.co.uk/cnc-hot-wire-foam-cutter/) has some good documentation on the machines he built and what he used to control them. Some of them use expensive software and outdate hardware, which might be difficult to find.
