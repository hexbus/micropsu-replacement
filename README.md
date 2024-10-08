# micropsu-replacement
This 1.0a version is a drop-in replacement for a ±12V and +5V micro power supply, requiring minimal soldering.

**Input:** Max 4A @ 12V regulated (use a high-quality supply).  
**Output:** +5V @ 3A (with DFR8031 slightly de-rated for heat dissipation), -12V @ 1A, and the remaining capacity to the 12V input.

While you **might** be able to exceed more than a total of 4A output by providing more than 4A input (i.e. 6A, so you can pull more than 12V from the 12V rail), it’s untested and unadvised — **you are on your own - proceed with extreme caution**.

This board is primarily designed for various low-voltage retro computer systems needing tri-voltage output (+5V, -12V, +12V), such as MSX systems, the Commodore Amiga, RS232 interfaces, and other perhipherals that needed tri-voltage power supplies.  The v1.0c versions of the board will offer a slightly more compact form factor and will allow a barrel 12V input option; it likewise is being tested as soon as the boards arrive.

This board a remix of [dabonetn's TI-99/4A replacement power supply project](https://github.com/dabonetn/ti99psu-replacement), which is based on jonn-reenthused's [TI99-4A-dc-power-board](https://github.com/jonn-reenthused/TI99-4A-dc-power-board). I’ve ported it from EasyEDA to KiCAD, but still haven't figured out the schematic part of KiCAD yet.  Please feel free to offer any merges with added schematics. 

(Note as of 9/20/2024 this 1.0b version of the board is untested - I am ordering prototype boards to verify its operation.)

Thanks to both authors for keeping these systems alive!

Original author notes (adapted for my board):

* 5V: This uses a DFR0831 5v buck converter, that's rated for +5v@4a, but I recommned no more than 3.5a draw.  You should also use a 2.5mm thermal pad underneath the DFR8031 to help cool it.
* -12V: -12v is provided with a P78E12-1000 switching regulator
* 12V:  Provided by a regulated 12V power supply.  Use a good one for input.  Do not exceed the cumulative 4A input.
* Use the recommended 560ohm resistor for a bright LED or 2.2k for a dull LED.
* The SUP53P06-20-E3 mosfet is there for reverse voltage input, but you can leave it out by connecting pins d & s ( the two close to the edge of the board)

![Current version](https://raw.githubusercontent.com/hexbus/micropsu-replacement/refs/heads/main/images/micropsu.png)
