# Simple SCART Breakout Board

![](balls.jpeg)

This is probably one of the most basic SCART breakout boards you can get. It's designed for the TV Desecrator, a project which is taking forever. But it might be
useful for other people's projects too.

## Bill of materials

Required:
* SCART female connector, vertical (NOT designed for right-angle connectors)
* 16-pin ribbon cable connector, 2x8, 2.54mm spacing

For the status LED:
* LED1: standard 5mm LED
* Q1: NPN transistor, SOT-23, B/E/C pinout
* R1: Transistor drive current limiting resistor, 0603, 1k ohms typical
* R2: LED current limiting resistor, 0603, 220-1k ohms typical

## Boring Ass Schematic

![](boring.png)

## Ribbon connector pinout

This will duplicate the docs in the TV Desecrator repo (when I care to upload it) but:

| Fcn         | Pin | Pin | Fcn       |
| ----------: | --: | :-- | :-------- |
|         +5V |   1 | 2   | +5V       |
|         GND |   3 | 4   | GND       |
| AUDIO RIGHT |   5 | 6   | RED       |
|  AUDIO LEFT |   7 | 8   | GREEN     |
|         GND |   9 | 10  | BLUE      |
|  RGB IN USE |  11 | 12  | GND       |
|         GND |  13 | 14  | GND       |
|   COMPOSITE |  15 | 16  | BLANKING  |

where:

* +5V is 5VDC from the TV Desecrator's 5 volt regulator
* GND is chassis ground
* AUDIO LEFT / AUDIO RIGHT are audio inputs
* RGB IN USE is a 5 volt TTL signal, active high, indicating that the TV Desecrator is pulling RGB video from this connector
* RED/GREEN/BLUE are 0.7 Vpp, 75-ohm terminated RGB video signals
* COMPOSITE is either a composite video signal or composite sync information
* BLANKING is the SCART blanking signal

This connector is designed so that, in the future, the breakout board can perform additional tasks if needed. I had sync stripping in
mind when I did this. However it's entirely possible that breakout boards can be daisy chained together.

## License

Public domain
