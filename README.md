# micropsu-replacement
This is a drop-in replacement for a ±12V and +5V micro power supply, requiring minimal soldering.

**Input:** Max 4A @ 12V regulated (use a high-quality supply).  
**Output:** +5V @ 3A (with DFR8031 slightly de-rated for heat dissipation), -12V @ 1A, and the remaining capacity to the 12V input.

While you **might** be able to exceed more than a total of 4A output by providing more than 4A input, it’s untested and unadvised — **you are on your own - proceed with extreme caution**.

This board is primarily designed for various low-voltage retro computer systems needing tri-voltage output (+5V, -12V, +12V), such as MSX systems and RS232 interfaces.

It's a remix of [dabonetn's TI-99/4A replacement power supply project](https://github.com/dabonetn/ti99psu-replacement), which is based on jonn-reenthused's [TI99-4A-dc-power-board](https://github.com/jonn-reenthused/TI99-4A-dc-power-board). I’ve ported it from EasyEDA to KiCAD, but still haven't figured out the schematic part of KiCAD yet.  Please feel free to offer any merges with added schematics. 

Thanks to both authors for keeping these systems alive!

Original author notes (adapted for my board):

* 5V: This uses a DFR0831 5v buck converter, that's rated for +5v@4a, but I recommned no more than 3.5a draw.  You should also use a 2.5mm thermal pad underneath the DFR8031 to help cool it.
* -12V: -12v is provided with a P78E12-1000 switching regulator
* 12V:  Provided by a regulated 12V power supply.  Use a good one for input.
* Use the recommended 560ohm resistor for a bright LED or 2.2k for a dull LED.
* The SUP53P06-20-E3 mosfet is there for reverse voltage input, but you can leave it out by connecting pins d & s ( the two close to the edge of the board)
