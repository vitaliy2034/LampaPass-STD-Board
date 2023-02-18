- Analog to digital part distance should be > 20h.
- For signal frequency above 10KHz return path is the same with signal path.
- Analog part of circuit should be placed in the corner of PCB, to prevent malfunction.
- To minimize EMI surround the PCB of ground strip(0.5/0.25 mm MINIMUM).

##  Tracks:
- Avoid 90 degree corners.
- Avoid trucks under components.
- Avoid power loops.
- After 10-20kHz return current will be directly under trace(because of increasing factor of frequency in Impedance Z= sqrt((R+jwL)/ (G + jwC)))
## Vias
- At least one power Via per pin.
- It is recommended to place power Via before bypass capacitor(s).
- Place same number of Vias on both power sides(ex. 2 vias for VCC and 2 vias for GND).
- Not place via near the pad(except you are yousing Via in Pad technology)
## Power nets:
- Power tracks should be wider than signal, even if supply current is small
- Always try to use polygons instead of tracks for power nets
- Voltage sens pin shoudnt be connected to power plane
- If signal use power plane as reference, power plane should be with same voltage source.   ***WHY***
## Phases of development:
- Place
- Connect pins(Vias first)
- Improve connections
- Pour planes

## To future:
If use signal-signal stackup, signals  on top layer should be sparated by ground lines/fils. Same with vias. If not enough space: put ground in middle andsurround.

For High speed signals through ground-power planes distance between should be 0.2mm max.

***WHY*** dont do power plane under analog circuit