# micropsu-replacement
This 1.0c version is a drop-in replacement for a ±12V and +5V micro power supply, requiring minimal soldering.

## Specifications:

**Input:** Max 4A @ 12V regulated (use a high-quality supply) via J1 (wires) or J3 (barrel input).

**Output:** +5V @ 3A (with DFR8031 slightly de-rated for heat dissipation), -12V @ 1A, and the remaining capacity to the 12V input via J2's four pin output.

While you **might** be able to exceed more than a total of 4A output by providing more than 4A input (i.e. 6A, so you can pull more than 12V from the 12V rail), it’s untested and unadvised — **you are on your own - proceed with extreme caution**.

## Background:

This board is primarily designed for various low-voltage retro computer systems and peripherals needing tri-voltage output (+5V, -12V, +12V), such as MSX systems, the Commodore Amiga, RS232 interfaces, the Corcomp 9900 sidecar, and other perhipherals that needed tri-voltage power supplies.  

### Latest Changes: 

Changes with 1.0c of the board is slightly more compact, has holes in it for mounting, and has a barrel 12V input option.  You may use the 12V J1 input OR the barrel 12V input.  DO NOT use both!

## Thanks: 

This board a remix of [dabonetn's TI-99/4A replacement power supply project](https://github.com/dabonetn/ti99psu-replacement), which is based on jonn-reenthused's [TI99-4A-dc-power-board](https://github.com/jonn-reenthused/TI99-4A-dc-power-board). I’ve ported it from EasyEDA to KiCAD, but still haven't figured out the schematic part of KiCAD yet.  Please feel free to offer any merges with added schematics. Thanks to both authors for keeping these systems alive, and to members of the Atlanta Historic Computing Society for supporting this project.

### Original author notes (adapted for my board):

* 5V: This uses a DFR0831 5v buck converter, that's rated for +5v@4a, but I recommned no more than 3.5a draw.  You should also use a 2.5mm thermal pad underneath the DFR8031 to help cool it.
* -12V: -12v is provided with a P78E12-1000 switching regulator
* 12V:  Provided by a regulated 12V power supply.  Use a good one for input.  Do not exceed the cumulative 4A input.
* Use the recommended 560ohm resistor for a bright LED or 2.2k for a dull LED.
* The SUP53P06-20-E3 mosfet is there for reverse voltage input, but you can leave it out by connecting pins d & s ( the two close to the edge of the board)

##BOM 

(Links lead to Mouser, but many items are much less expensive on Aliexpress, 14 items total):

* SW1:  [500SDP1S1M2QEA](https://www.mouser.com/ProductDetail/E-Switch/500SDP1S1M2QEA?qs=%252BZnE%2FxbLNR9K23nY3Tws9g%3D%3D) E-Switch DPDT, 4A minimum, PC-PIN or equivalent 
* J1: 	[09652028](https://www.mouser.com/ProductDetail/Molex/09-65-2028?qs=sGAEpiMZZMvlX3nhDDO4AMj2eUq01hUX%252BAhYX12ZlRg%3D) 2-pin 3.96 Molex
* J2:	[26604040](https://www.mouser.com/ProductDetail/Molex/26-60-4040?qs=tRPrwvvr%2FuiQpDQcO3P3Lw%3D%3D) 4-pin 3.96 Molex
* J3:	[WE 694106301002](https://www.mouser.com/ProductDetail/Wurth-Elektronik/694106301002?qs=a9WhcLg8qCwOEkcI62k5mA%3D%3D) DC Barrel connector 2.5/2.1MM
* Q1:	[FQP47P06](https://www.mouser.com/ProductDetail/onsemi-Fairchild/FQP47P06?qs=ZS9em9a1DI4QoVAAU1ygLw%3D%3D) Mosfet for reverse protection - also, much cheaper in bulk on Aliexpress.
* R1:	[560 ohm 1/4 resistor](https://www.mouser.com/ProductDetail/YAGEO/CFR-25JT-52-560R?qs=sGAEpiMZZMsPqMdJzcrNwslF2s3r2P4uPdiIn5eV7%252BI%3D)
* [DFR0831](https://www.mouser.com/ProductDetail/DFRobot/DFR0831?qs=iLbezkQI%252BsjsPFkttXQbEA%3D%3D): 30 and lower to 5V step down, 4A.  Also known as "Mini 560". Highly suggest a thermal pad between the back of this and the board.
* LED1: Regular LED (any kind, color)
* Capacitors: (2) [10uf, 25V](https://www.mouser.com/ProductDetail/667-ECA-1EM100), 2.0mm lead spacing, (3) [22uf, 16v](https://www.mouser.com/ProductDetail/667-ECE-A1EKA220), 2.0mm spacing
* VR1: 	(Not marked):  -12V P78E12-1000 DC-DC converter or [LM7912](https://www.mouser.com/ProductDetail/Texas-Instruments/LM7912CT-NOPB?qs=QbsRYf82W3GCP0%2FQjKEJfQ%3D%3D) 1A -12V converter.  Please Note:  CUI is working on a successor to the P78E12-1000.  The current recommended replacement does NOT support negative voltage.
  
![Current version](https://raw.githubusercontent.com/hexbus/micropsu-replacement/refs/heads/main/images/micropsuv1.0c.png)

![Constructed Version](https://raw.githubusercontent.com/hexbus/micropsu-replacement/refs/heads/main/images/1.0c.png)
