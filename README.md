# Pen-Plotter
Reconfigured Marlin (commonly used for custom 3D printers) firmware for CNC-style pen plotting. This project was recreated from an existing food 3D printer running Marlin firmware by removing the syringe used for paste extrusion and replacing it with a makeshift pen carriage instead.

As this is a branch-off project off of the Food 3D Printer (https://github.com/johnathantran/Marlin-Food-3D-Printer), it uses the exact same hardware and software (with the exception of the pen carriage and Repetier instead of Pronterface). Therefore, for detailed instructions on how to set up the physical build, wire the electronics, and program the Arduino, please refer to the Assembly Instructions PDF in the Food 3D printer repo.

## Electronics Materials:
- 1x Arduino Mega
- 1x RAMPS 1.4 Shield
- 1x 12V DC Power Supply
- 3x DRV8825 Motor Drivers
- 3x NEMA17 Stepper Motors
- 2x Limit Switches
- 9x Microstepping Jumpers

## Software
- Arduino IDE
- Marlin firmware (flash the Marlin.ino file to your Arduino): https://github.com/MarlinFirmware/Marlin
- Inkscape (used for converting SVG files to g-code): https://inkscape.org/release/inkscape-1.0/
- Repetier Host (used to run the g-code): https://www.repetier.com/download-now/
- Adobe Illustrator G-code Panel (untested but interesting): https://diegomonzon.com/illustrator-to-g-code-panel

## Workflow
This is a general workflow of how to convert an image (SVG) file to g-code that can be interpreted by the pen plotter. In-depth instructions can be found in this guide: https://medium.com/@urish/how-to-turn-your-3d-printer-into-a-plotter-in-one-hour-d6fe14559f1a

### Free SVG Files Online
The following websites provide free SVG files. You can also make your own SVG files in Adobe Illustrator.
https://publicdomainvectors.org/

https://lovesvg.com/

### Inkscape
1. Adjust Document Settings to match the width and height of your canvas to your drawing bed.
2. Import an SVG file of your choice as an object.
3. Remove the Fill color from the object and give it a Stroke outline.
4. Add Orientation points using Gcodetools extension and adjust accordingly.
5. Generate gcode using Gcode to Path.

### Repetier
5. Load the g-code file into Repetier. If the object is not oriented properly, go back to Step 4, change your Orientation points, and generate a new g-code file.
6. Home axes.
7. Run print.

## Full Wiring Diagram:
![Wiring Diagram](https://github.com/johnathantran/Pen-Plotter/blob/master/FullWiring.png)

## Full Build
![Final Build](https://github.com/johnathantran/Pen-Plotter/blob/master/FullBuild.jpg)

## Makeshift Pen Carriage
I know that this is a very low-res prototype for a pen carriage, but it will have to do until I get access to a 3D printer to custom-make one :)
![Makeshift Pen Carriage](https://github.com/johnathantran/Pen-Plotter/blob/master/Carriage.jpg)

## Drawing Samples
Sample 1:
![Sample 1](https://github.com/johnathantran/Pen-Plotter/blob/master/Sample1.jpg width=100)

Sample 2:
![Sample 2](https://github.com/johnathantran/Pen-Plotter/blob/master/Sample2.jpg width=100)
