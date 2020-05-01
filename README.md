# Anthony's 3D Printer Guide
An instructional, step-by-step guide to building my version of the popular Hypercube printer, which can be found at: https://www.thingiverse.com/thing:1752766. Tech2C (the original creator) does a great job of setting a foundation that I've modified and improved upon and created a guide to augment his. I'd recommend reading his guide and watching his videos first, and then reading this one to get a deeper understanding of its mechanical function as well as modifications and improvements that can be made. A **quick disclaimer**: as of today, desktop 3D printers have achieved such high quality for their price that building one will not only be more expensive, but also likely result in a poorer product. To me and many other makers, however, it is definitely more fun to build one yourself, but if you're just looking to get started printing without much effort I'd recommend buying a printer.

## Gathering the Parts
The first part of any build is to gather all the parts! A full parts list can be found at the thingiverse link, but lets take some time to properly understand what even we're buying and what each part does. We'll start with the printed parts, since those are probably the hardest ones to source.

### 3D Printed Parts
Unfortunately, it is virtually impossible to build a 3D printer without access to 3D printer to fabricate many of the needed brackets, mounts, and gantries. The full list of printed parts needed can be found at the thingiverse link, and for convenience I've uploaded the files to the repo. If 3D printing is a concern, there are a lot of shortcuts that you can get away with. In my personal design, I found it easier to buy a $15 dollar extruder from Amazon, which removes the need for printing the three Bowden parts. If you're willing to make liberal use of duct tape, there are many other parts that you could shortcut, including:

1. Z, X, Y endstops: In a pinch you can glue or tape the endstops on without the need for a printed mount
2. Sensor mounts: A inductive sensor is a bit of a luxury, since automatic bed leveling isn't a must to print parts
3. Z endstop adjust: This can be emulated with glueing or taping a screw on your bed. (This'll become obvious later)
4. Spool axle clamp: Technically you don't need this, but you will have to figure out an alternate way to hold your spool.

This reduces the amount of needed printed parts, but sacrifices a bit of functionality and quality, which can be a worthwhile trade if printed parts are hard to come by. I'd recommend looking at local makerspaces of if needed, use a 3D-printing service.

### Aluminum Extrusion
Now onto the commercically available parts. Aluminum extrusion can be sourced reasonably from Amazon, Misumi, Mcmaster or other manufacturers, but the challenge here is how to cut them to length. Your best bet is either a horizontal bandsaw, vertical bandsaw or chopsaw, but those require access to a well-equipped metal shop. If those machines are out of the option, you could spend an afternoon getting a massive arm workout and manually hacksaw all the extrusions down to length. Alternatively if you're willing to shell out a little more money, you could pay the manufacturer to cut extrusions down to length.

### Linear Motion
Onto the parts needed for linear motion. Again, I would look into buying the metals rods from the manufacturer such that they arrived at the pre-specified length. If not, I would caution against ordering hardened steel rods, as they cannot be easily cut down to size. It's nearly impossible to hand-machine and requires expertise with a chopsaw to properly cut. Aluminum is a bit more expensive and difficult to find, but using aluminum for the Y and Z motion can be worthwhile investment. All the other components here are easily sourced and ready to use out of the box, there shouldnt be issues with it.

### Specialty Hardware
Just a quick note on 3D-printing specific hardware. The recommended hotend is the E3D V6 with the standard heater block. The original guide also gives a large amount of freedom with the choice of an extruder and recommends a stock MK3 aluminum heatbed. Since your extruder/hotend combo will dictate many of the printing capabilities of your printer (speed, quality, acceptable filaments), and your heat bed will likely determine your first layer adhesion, these are important decisions worth looking into a bit. The V6 hotend is probably the most basic viable hotend for a printer. It's a great product that many legitimate 3D printing companies use to build their printers. It's also one of the more expensive parts of the printer at around 60 dollars, but it's well worth it. There are many clones and knockoffs, costing around 20 dollars, but the amount of problems that'll arise using those is not worth saving the money. Alternatives to the V6 are its counterparts with different heater blocks such as the E3D Volcano. Now for the extruder. If you don't want to build your own, I would recommend using and Ender 3 style extruder (MK8) since its cheap and works perfectly fine. If you want a more quality extruder to print flexible filaments, I'd recommend spending the money and buying a Bondtech BMG extruder. It's around 80 dollars but will likely outlast all other components on your printer. For the bed, I would recommend skipping the stock MK3 bed since it's lack of a bed coating means that it'll be much more likely for adhesion problems to arise. I'd recommend an Ultrabase, or buying some sort of bed liner like BuildTak or a PEI steel sheet. 

### Electronics
With the screws, there isn't anything special. However, I'd like to take a moment to consider the electronics. The stock motor drivers recommended is the A4988. A few years ago, this motor driver would be the only viable choice, since higher-end stepper drivers would cost a fortune. However nowadays, Chinese manufacturers have somehow found ways to emulate German Trinamic drivers such that high-quality TMC drivers are now available inexpensively. If you want a nicer printer that makes less noise and has smoother motion, and are willing to pay ~20 more dollars, I'd recommend either buying TMC2208 or TMC2130 drivers. These take more time to set up eletronically as well, but it could be worth it. Another important point is the main board of the printer. Tech2C lists the SKRv1.3 as the recommended board, but this board is generally difficult to setup since it runs on a 32-bit version of Marlin. Less people use Marlin 2.0, as as such, there is a smaller support community for debugging issues with it. If you're new to 3D printing, I would recommend using the inexpensive Arduino Mega/RAMPS 8-bit board combo, which is much easier to set up. The inductive sensor is also optional, but recommended since its relatively inexpensive. 

## Mechanical Assembly
After you gather all the parts, we can finally start building the printer. The first step would be to assemble the frame and bed.

### Assembling the Frame
I think this part is pretty self-explanatory, there really isnt much nuance or tricks to assembling the frame. I think Tech2C does a great job of explaining this part, and you just have to take the time to sit down, square everything off, and bolt everything together. 

### Assembling the Gantries
The gantries can be difficult to assembly due to the amount of aligning that needs to be done between the rods. I'd recommending setting up the X gantry first and making sure that the X slider can move smoothly along either the carbon fiber rod or aluminum rod (depends on which you buy). The copper lubricated linear bearing or IGUS bearing is generally not that great at sliding along the rods at first, since the embedded drops of lubricant actually need to be released by wear and tear. I'd recommend using some sort of grease to help in this process, and maybe even sand down the diameter of the rods if there is severe binding. Another thing that could cause binding is the two rods are slightly skew after assembly. In this case, it's pretty easy to slightly bend the rods one way or another to adjust them to be parallel again. Other than that, the LMU8 and LMU12 bearings tend to be pretty good in sliding along the rods and shouldn't pose much trouble for the Y and Z gantries.

### Assembling the Motors and Belts
The motors and and belts are relatively easy to assemble, since the frame and supporting geometries are already in place to properly align and install the motors+belts. For the belt, it is important to properly tension it during this step, since it's really difficult to adjust tension later and a loose belt can really affect print quality. Don't forget the extruder and Z motor!

![Image of CoreXY](https://github.com/anthonyzhou-1/3Dprinting/blob/master/corexy.jpg)

### Assembling Miscellaneous Hardware
By this point, you should have a functional XYZ gantry that is driven by stepper motors. To finish the build, you still have to assemble the hotend, endstops, fans, sensors (if using), spool holder, and mount the electronics. E3D's guide on assembling the V6 hotend is great and is pretty easy to follow. All the other bits of hardware are pretty self-explanatory and Tech2C does a good job of explaining it. 

## Setting up the Electronics
Depending on the mainboard and stepper drivers you've chosen this is going to look a bit different, but the process is more or less the same.

### Mega/RAMPS Setup with A4988 Drivers
This is probably the simplest setup. Just follow the wiring diagram below:

![Image of RAMPS](https://github.com/anthonyzhou-1/3Dprinting/blob/master/ramps.png)

The only caveat is **make sure you short the appropriate pins under each driver**. If you don't do this, the printer will default to full stepping mode, it will be near unusable. I'd recommend 1/16 stepping since the Arduino Mega in general cannot handle lower stepping modes.  The table of pins to short is shown below.

1     2    3 \
no   no    no    full step\
yes  no    no    half step\
no   yes   no    1/4 step\
yes  yes   no    1/8 step\
no   no    yes   1/16 step\
yes  no    yes   1/32 step\
no   yes   yes   1/64 step\
yes  yes   yes   1/128 step

The only other thing to pay attention to is adjusting the potentiometers on the A4988 drivers to limit the output current of the driver. A good guide by E3D is here: https://e3d-online.dozuki.com/Guide/VREF+adjustment+A4988/92. This is an important step since if you give your motors too much current, they can overheat and if you give it too little current, they won't have the torque to move your gantries.

**Before powering on the board, make sure the input voltage is the correct polarity and the motor drivers and installed correctly** Doing any of these things wrong will destroy your electronics.

Once powered on, I'd recommend quickly writing an Arduino program to control a stepper motor. A good guide for doing that is here: https://howtomechatronics.com/tutorials/arduino/how-to-control-stepper-motor-with-a4988-driver-and-arduino/. The pinouts from the Mega to RAMPS shield can be found below. (Just reference the pinout on the Mega connection to the correct pin on the stepper drivers)
![Image of RAMPSpinout](https://github.com/anthonyzhou-1/3Dprinting/blob/master/rampspinout.png)

Once your stepper can move, it's a pretty good indication that the board is running as it should be.

### SKRv1.3 Setup with TMC Drivers
If you chose the SKR v1.3 as the mainboard, the setup is more or less similar. The diagram below explains it well: 
![Image of SKRv1.3](https://github.com/anthonyzhou-1/3Dprinting/blob/master/skrv1.3.jpg)

With the SKR v1.3, the pins to short are more complicated, since in addition to each setting each driver's stepping mode, you also have to short pins to set how the board interacts with each driver. TMC drivers have the capability to detect large spikes in counter EMF, which is useful to home the printer without hardware endstops, but this capability must be enabled by shorting the correct pins. Alternatively, you can forgo this setup and use the TMC drivers as you would a standard stepper driver. The guide that comes with purchasing an SKRv1.3 board is great at explaining this. 

Unfortunately, there isn't an easy way to upload software to the 32-bit board and test the stepper motors, so testing will have to occur after installing firmware.

## Uploading Firmware
The steps for uploading firmware to your board will differ again based on if you've used an 8-bit board or a 32-bit board. It is substantially easier with an 8-bit board, since this setup is more common among DIY 3D printers and as such has a much bigger community to provide support. Furthermore, Arduino's programming environment and process for uploading firmware is designed around an easy and streamlined user experience. The recommended firmware to run is Marlin, but it is possible to run other firmwares like Repetier or for 32-bit boards, Smoothieware. As such, I'll be focusing on how to setup Marlin. They have a great auto-build tool that can be found here: https://marlinfw.org/docs/basics/install_platformio.html, but it requires a bit of setup and if you'd rather do it manually the steps are below.

### Arduino Mega/RAMPS Setup
Marlin has as great guide on how to get started here: https://marlinfw.org/docs/basics/install_arduino.html. Before uploading to your Mega you'll have to configure the Marlin firmware in the configuration.h file. Again, Marlin has a good guide here: https://marlinfw.org/docs/configuration/configuration.html. It mostly depends on commenting or uncommenting commands and also setting variables to specific values. A challenging part of the config can be setting the correct steps/mm of your axes, but the Prusa calcaultor does a good job of doing all the math for you: https://blog.prusaprinters.org/calculator/. A note on the configuration: while it is pretty straightforward, it is important to carefully read through all the options and set them correctly. The majority of issues that arise in building a 3D printer arise from a faulty config file. The hardware and electronics tend to be quite reliable, and since the config file can often be overwhelming it is easy to make a mistake there. After doing this, I would test the upload by connecting through the Arduino serial terminal and sending an M119 command to read the state of the endstops. This is a great non-destructive command to use to check serial connection, and if everything is good send a M502 followed by M500 to initialize the EEPROM data.

### SKRv1.3 Setup
Marlin 2.0 by default can run on both 8-bit and 32-bit boards, but the process of uploading to a 32-bit board is a bit different and more complex. A pretty good guide on how to do this is here: https://marlinfw.org/docs/basics/install_rearm.html, although there are some caveats to keep in mind. PlatformIO tends to run better on Microsoft Visual Studio as opposed to Atom. Furthermore, unlike the Arduino programming environment, it isn't as easy just to press a button and have the firmware uploaded to your board. If you've formatted the SKRv1.3's internal microSD card correctly, when connected to it from your laptop, its internal microSD card should show up in the file explorer. However, this is not always the case, and alternate method for uploading firmware is to take the internal microSD card out and manually insert it into your computer through a microSD to SD card adapter. You can then put the firmware.bin file onto the microSD and then physically re-insert it into the mainboard. Upon resetting the board, the firmware should boot. At this point, I'd recommend installing some sort of terminal program, such as Pronterface or Repetier-Host, and test an M119 command to read the state of the endstops. Again, if everything is good, send a M502 followed by M500 to initialize the EEPROM data.

## First Tests and Calibration
Congrats on getting the printer functional! At this point, you could print something, but to increase the quality and longevity of your printer, it's good to run a few simple tests and calibrate the settings of the printer.

### Simple Tests 
Either using gcode commands or Marlin's interface on the LCD, I'd recommend testing these features:
1. Moving X, Y, Z axes
2. Heating up hotend
3. Extruding filament
4. Turning on part cooling fan
5. Heating up bed
6. Checking if endstops trigger
7. Check inductive sensor (if using)
8. Check XYZ homing procedure

At this point, I would install a slicer of your choice. I'd recommend Cura, Slic3r or Ideamaker, which are all solid free to use choices.

### Calibrating First Layer
If you don't have an inductive sensor or some other auto bed-leveling feature, this step is important in making sure your first layer sticks to the bed. Simply move to one of the four corners and slip a piece of regular printer paper under the nozzle. Zero the Z-axis and adjust the bed leveling screws such that there is barely any resistance between the nozzle, bed, and paper. Repeat this process for the rest of the corners. In cases where the nozzle is way too far or too close to the bed, adjust the hardware Z offset such that the bed will contact the Z endstop at a different height and thus set a different zero. 

### Calibrating Steps/mm
In theory, the steps/mm of your stepper motors should be exactly what the calculator outputs, but in reality a lot of factors can affect this value. To calibrate this value, a 20 mm XYZ calibration cube is usually used: https://www.thingiverse.com/thing:1278865. After printing, measure each dimension with a pair of calipers, scale the steps/mm appropriately in the firmware, and reupload the firmware.

### Calibrating Extrusion Multiplier
Another important setting to calibrate is the extrusion multiplier of the printer. In theory, the extrusion width of each line of filament extruded is the diameter of the nozzle, but again this is not practically the case. A simple model to print that will help with finding an extrusion multiplier can be found here: https://www.thingiverse.com/thing:2490893. On some slicers, this setting is called flow or flow multiplier, and usually ranges between 90-110%.

### Checking Print Quality
So far, the two calibrations were focused on bringing dimensional accuracy to the printer, but there are a host of other settings to become familiar with in order to produce high-quality prints. (Print speed, hotend temperature, retraction settings, cooling, etc.) A good way to get familiar with these settings and find their optimal values is to print a benchy: https://www.thingiverse.com/thing:763622. There are plenty of guides online that help diagnose your benchy and depending on the quality of the resulting print, you will probably have to adjust and re-print the model.

### Diagnosing Common Problems
3D printing is a really exciting process, but you will invariably encounter problems both with print quality and prints failing. Below I've compiled a list of common problems and how to deal with them, but it is in no way comprehensive. 

1. Prints not adhering the bed: This can be caused by a lot of factors such as bed temp and filament material. However, the most common issue is the bed is not leveled. I would manually re-level the bed or set a different Z-offset if using a auto bed-leveling probe. If this still doesn't solve the problem some generic gluestick should help prints adhere to the bed when applied before printing. Another fix is adjusting with the bed temp according to the filament printed. Some filaments require temperatures up to 100 degrees Celsius to print, while others can adhere without any heating at all. In general, make sure to print first layers at slow speeds so that the first layer can properly adhere.

2. Prints warping off the bed: This is usually caused by a large temperature drop between the bed and the surrounding environment causing the edges/corners of the print to peel away from the bed. A simple way to fix this is to print a brim around the object to increase the first layer adhesion. Alternatively, you could also use a gluestick to further increase adhesion or in some cases, up the bed temperature.

3. Stringing: This is usually a problem with either flexible filaments or PETG. I would recommend increasing retraction distance and speed, or looking for specific filament profiles online to dial in the correct retraction settings. Furthemore, increasing travel speed can reduce the chance for strings to form between features. Alternatively, you could simply use a heat gun to melt off the strings in post-processing.

4. Melted/Warped features: This is usually characterized by sagging features caused by a lack of cooling. Thin features are especially susceptible since they don't have much time to cool before a new layer is added on. In this case, the filament sags since it hasn't had time to harden, and an easy fix is to simply up the cooling, or if the cooling is already at max, slow down the print speed.

5. Blobbing/Poor surface finish: This can have a variety of factors that cause this issue. You could be printing too fast and not giving enough time for the plastic to properly melt in the heater block, which would cause the extruded plastic to not properly follow the contour of the printhead. In this case, up the hotend temp and print slower. Furthermore, you could have insufficient cooling, which would could allow the extruded plastic to slightly move before it solidifies. Overextrusion is also a possible cause, since extruding too much plastic tends to lead to blobs of excess plastic forming on the surface. A good surface finish often requires a lot of tuning and adjusting of print settings.

6. CLogged Nozzle: This one kinda sucks to have and takes a bit of effort to fix. The first thing I would try is to heat the extruder to around 250 degrees Celsius and try to push the filament through by hand as hard as you can. If this doesn't do anything, I would take something like an acupuncture needle or other thin object and try to poke at the nozzle's outer hole. If this still doens't clear the clog, you can try an cold pull. As the hotend cools down, at around 100-150 degrees Celsius, you can try to pull the filament out and hopefully the clogged plastic will emerge as a solid piece. If you've been printing in ABS, you can try dissolving the clogged plastic by putting the clogged nozzle in acetone. If all hope is lost, just buy a new nozzle for around 5-10 dollars. 

By this point, you should have a fully functional printer capable of producing repeatable, high-quality parts. 

# Happy Printing!










