
# Odroid N2+ Woodcase
A small wooden case suitable for the Odroid N2+ from Hardkernel.
There are many cases online that you can buy or 3D print for the N2+, but I didn't like any of these.
I wanted a compact and stylish case for the Odroid so I could place it on my TV shelf.
I run an Android on the Odroid as Chromecast replacement and Multimediacenter.

I created the case based on a 3D model in Fusion360 and saved the cutting patterns as DXF files.
Feel free to make your own little woodcase for your Odroid!

## File Overview

- DXF Files: individual patterns for each side as .dxf file, without labeling
- LaserDraw Files: All patterns in two files. one for the sides with labels, and one file for the cover.

## How to build the Woodencase

###Things you need
**tools**
- Lasercutter
- soldering iron
- electric craft tools like Wire cutters, stripping pliers, etc
**material**
- TTP223 capacitive touch sensor (available on Ebay, Amazon, etc.)
- Around 120x120mm MDF 3mm or another wooden material
- Around 110x110mm plexiglass 2mm or another material
- cable to connect the sensor
- glue to attach the touch sensor



### Configure Touchbutton on Odroid
1. Open the eMMC Storage on your computer
1. Open env.ini
2. exclude `gpiopower="479"`

### Connect the Touchbutton
Pin 1: 3.3V
Pin 9: GND
Pin 11: POWER_SWITCH
