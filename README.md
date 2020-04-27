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

### Electronics
With the screws, there isn't anything special. However, I'd like to take a moment to consider the electronics. The stock motor drivers recommended is the A4988. A few years ago, this motor driver would be the only viable choice, since higher-end stepper drivers would cost a fortune. However nowadays, Chinese manufacturers have somehow found ways to emulate German Trinamic drivers such that high-quality TMC drivers are now available inexpensively. If you want a nicer printer that makes less noise and has smoother motion, and are willing to pay ~20 more dollars, I'd recommend either buying TMC2208 or TMC2130 drivers. These take more time to set up eletronically as well, but it could be worth it. Another important point is the main board of the printer. Tech2C lists the SKRv1.3 as the recommended board, but this board is generally difficult to setup since it runs on a 32-bit version of Marlin. Less people use Marlin 2.0, as as such, there is a smaller support community for debugging issues with it. If you're new to 3D printing, I would recommend using the inexpensive Arduino Mega/RAMPS 8-bit board combo, which is much easier to set up. The inductive sensor is also optional, but recommended since its relatively inexpensive. 

## Mechanical Assembly
After you gather all the parts, we can finally start building the printer. The first step would be to assemble the frame and bed.

### Assembling the Frame
I think this part is pretty self-explanatory, there really isnt much nuance or tricks to assembling the frame. I think Tech2C does a great job of explaining this part, and you just have to take the time to sit down, square everything off, and bolt everything together. 

### Assembling the Gantries







