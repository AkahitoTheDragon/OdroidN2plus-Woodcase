
# Odroid N2+ Woodcase

![IMG_20220929_173057](https://user-images.githubusercontent.com/74838190/193081744-4a20eb48-53ef-48c4-8d56-eca315350ece.jpg)

A small wooden case suitable for the Odroid N2+ from Hardkernel.
There are many cases online that you can buy or 3D print for the N2+, but I didn't like any of these.
I wanted a compact and stylish case for the Odroid so I could place it on my TV shelf.
I run an Android on the Odroid as Chromecast replacement and Multimediacenter.

I created the case based on a 3D model in Fusion360 and saved the cutting patterns as DXF files.
Feel free to make your own little woodcase for your Odroid!

**In theory, the case also fits the Odroid N2, but I can't test this! You are welcome to try out whether the case fits, as far as I know the circuit boards and the cooler are identical.**

## Table of Contents
1. [File Overview](#File-Overview)
2. [Things you need](#Things-you-need)
3. [Cut out the patterns](Cut-out-the-patterns)
4. [Preparing the touch sensor](Preparing-the-touch-sensor)
5. [Configure Touchbutton on Odroid](#Configure-Touchbutton-on-Odroid)
6. [assemble the woodcase](#assemble-the-woodcase)
7. [Disassembling the case](#Disassembling-the-case)



## File Overview

- DXF Files: individual cutting patterns for each side as .dxf file, without labeling
- LaserDraw Files: All cutting patterns in two files. one for the sides with labels, and one file for the cover.

## How to build the Woodencase

### Things you need

**tools**

- Lasercutter
- soldering iron
- electric craft tools like Wire cutters, stripping pliers, etc
- small file
- 
**material**

- TTP223 capacitive touch sensor (available on Ebay, Amazon, etc.)
- Around 120x120mm MDF 3mm thickness
- Around 110x110mm plexiglass 2mm thickness
- cable to connect the sensor
- glue to attach the touch sensor

### Cut out the patterns
Use a Lasercutter to cut out the faces. I used a EpilogLaser Fusion M2 with LaserDraw as Software.
I've created a cut pattern for LaserDraw with labeling (.CDL Files). Alternatively, i've uploaded the .dxf files of all faces individually, these are without labeling.
I use 3mm MDF plates for the case and 2mm Plexiglas for the lid. feel free to use any material, only the strength of 3mm/2mm is important!
After cutting it should look like this:

![IMG_20220929_161642](https://user-images.githubusercontent.com/74838190/193081667-47efaff8-36b8-4cd6-a178-0c77bc36ff02.jpg)

### Preparing the touch sensor
I use a TTP223 touch sensor as a power button, which is attached in the front behind the power symbol. You can get them for little money, for example. at amazon, ebay and co.
Solder bridge A must be connected so that the sensor switches Active Low, which is what the Odroid needs to power up/down. You should also remove the small LED which is not needed.

![IMG_20220929_163123](https://user-images.githubusercontent.com/74838190/193086811-fa5df39c-1f2e-4b13-8cb5-8e82b6bf60b3.jpg)

Then solder some cables to the connectors so that you can later connect them to the GPIO pins. Make sure these are long enough (see next step where to connect the sensor). I crimped on shortened Dupont connectors, but you can also solder the wires directly to the GPIOs

Make a mark on the back of the front piece just below the first prongs on the left side, the touch sensor should be glued under this line so it doesn't touch the lid.

![IMG_20220929_163742](https://user-images.githubusercontent.com/74838190/193093343-52178366-37ae-4e11-85e9-b82ec971988c.jpg)

Then glue the sensor with the touch surface under the marking. The sensor protrudes a little into the opening of the SD slot.

![IMG_20220929_171742](https://user-images.githubusercontent.com/74838190/193093805-0de3d484-e011-42b1-9584-b79ceaaf332c.jpg)

connect the touch sensor as follows:
|Pin  |       |
|-----|-------|
|1    |3.3V   |
|9    |GND    |
|11   |Signal |

*See also: [Odroid N2 Pinout](https://wiki.odroid.com/odroid-n2/hardware/expansion_connectors)*

![IMG_20220929_163810](https://user-images.githubusercontent.com/74838190/193089502-703b6e89-e271-4079-9a35-ce9dbf6e47dc.jpg)

In the end it should look like this:

![IMG_20220929_172106](https://user-images.githubusercontent.com/74838190/193094098-d194d03d-fbb1-4b43-9efa-fc429bb71d75.jpg)

### Configure Touchbutton on Odroid

I assume that you already have an operating system installed on your Odroid. I downloaded the Android self-installation image from [OdroidWiki](https://wiki.odroid.com/odroid-n2/os_images/android/android#tab__bit_android) and installed it on my eMMC.

[Instructions for Power Button from Odroid Wiki](https://wiki.odroid.com/odroid-n2/application_note/gpio/gpio_key_wakeup)

Unfortunately, the instructions from the OdroidWiki didn't work with Android, I found the following solution:

1. Open the eMMC Storage on your computer via USB Adapter
1. Open env.ini
2. search for `gpiopower="479"` and exclude

### Step 4: assemble the woodcase

Take one of the side parts and press the lid with force but carefully into the provided gaps.
Do the same with the other side, be careful not to break off the side pieces and only apply pressure where the lid is.

![IMG_20220929_163432](https://user-images.githubusercontent.com/74838190/193092415-846eb300-2043-494f-9d40-eea70a34cc3f.jpg)

Gently press the rail cutouts on the side panels onto the corresponding rail at the heatsink.

![IMG_20220929_172533](https://user-images.githubusercontent.com/74838190/193099463-bc42ba5b-638c-4c89-9b5b-2e4b8366cca0.jpg)

Put in the front and back panels last. Deburr the circuit board beforehand, I still had the burrs from production, I removed them with a small file.
The parts are measured very precisely, you need to use some force to push in the tines. However, be careful not to break anything.

![IMG_20220929_173057](https://user-images.githubusercontent.com/74838190/193101312-28208943-8a35-448a-90a6-3764d716066a.jpg)

Here we go, the wooden case is finished!

## Disassembling the case
The case is only sticked together and can theoretically be disassembled again, you have to be very careful because the parts are so tight together that something can quickly break off!
Make sure you don't have to get to the RTC battery or the eMMC memory that often.
