
# Odroid N2+ Woodcase

![IMG_20220929_173057](https://user-images.githubusercontent.com/74838190/193081744-4a20eb48-53ef-48c4-8d56-eca315350ece.jpg)

A small wooden case suitable for the Odroid N2+ from Hardkernel.
There are many cases online that you can buy or 3D print for the N2+, but I didn't like any of these.
I wanted a compact and stylish case for the Odroid so I could place it on my TV shelf.
I run an Android on the Odroid as Chromecast replacement and Multimediacenter.

I created the case based on a 3D model in Fusion360 and saved the cutting patterns as DXF files.
Feel free to make your own little woodcase for your Odroid!

## File Overview

- DXF Files: individual cutting patterns for each side as .dxf file, without labeling
- LaserDraw Files: All cutting patterns in two files. one for the sides with labels, and one file for the cover.

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

### Step 1: Cut out the patterns
Use a Lasercutter to cut out the faces. I used a EpilogLaser Fusion M2 with LaserDraw as Software.
I've created a cut pattern for LaserDraw with labeling (.CDL Files). Alternatively, i've uploaded the .dxf files of all faces individually, these are without labeling.
I use 3mm MDF plates for the case and 2mm Plexiglas for the lid. feel free to use any material, only the strength of 3mm/2mm is important!
After cutting it should look like this:

![IMG_20220929_161642](https://user-images.githubusercontent.com/74838190/193081667-47efaff8-36b8-4cd6-a178-0c77bc36ff02.jpg)

### Step 2: (Optional) Preparing the touch sensor
I use a TTP223 touch sensor as a power button, which is attached in the front behind the power symbol. You can get them for little money, for example. at amazon, ebay and co.
Solder bridge A must be connected so that the sensor switches Active Low, which is what the Odroid needs to power up/down. You should also remove the small LED which is not needed.

![IMG_20220929_163123](https://user-images.githubusercontent.com/74838190/193086811-fa5df39c-1f2e-4b13-8cb5-8e82b6bf60b3.jpg)

Then solder some cables to the connectors so that you can later connect them to the GPIO pins. Make sure these are long enough (see next step where to connect the sensor). I crimped on Dupont connectors, but you can also solder the wires directly to the GPIOs.

### Step 3: Connect the touch sensor
connect the touch sensor as follows:
|Pin  |       |
|-----|-------|
|1    |3.3V   |
|9    |GND    |
|11   |Signal |

### Configure Touchbutton on Odroid
1. Open the eMMC Storage on your computer
1. Open env.ini
2. exclude `gpiopower="479"`

### Connect the Touchbutton
Pin 1: 3.3V
Pin 9: GND
Pin 11: POWER_SWITCH
