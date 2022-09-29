
% Odroid N2+ Woodcase


# Files

- DXF Files: individual patterns for each side as .dxf file, without labeling
- LaserDraw Files: All patterns in two files. one for the sides with labels, and one file for the cover.


## Configure Touchbutton on Odroid
1. Open the eMMC Storage on your computer
1. Open env.ini
2. exclude `gpiopower="479"`

## Connect the Touchbutton
Pin 1: 3.3V
Pin 9: GND
Pin 11: POWER_SWITCH
