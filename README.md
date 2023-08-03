# kiteTRAK-for-PhobGCC

![kiteTRAK_small](https://github.com/kiteCTRL/kiteTRAK-for-PhobGCC/assets/68704631/4c2265f8-7842-4f7e-8d78-8f7caa818333)

## Hardware
* PhobGCC 2.x board
* 0.91" 128x32 SSD1306 display (https://a.co/d/0wZnROs)
* (4x) ~7" long wires
* Soldering equipment
* Clear back plate GCC shell

## Setup
This display connects to the GPIO breakout pins between the RP2040 chip and the ABXY button pads. When making your wires for the controller to display connection, consider the wire routing shown here:

![wire_routing](https://github.com/kiteCTRL/kiteTRAK-for-PhobGCC/assets/68704631/ebb46b6b-e7ee-47dc-8868-d6b00e7ad088)

Connections:
* GND -> GND
* VCC -> 3.3v
* SCL/SCK -> GPIO 13
* SDA -> GPIO 12

By default, the display is upright when the display's through holes are closer to the controller cable side (see main.cpp for reorienting the display). For keeping the display in place, use a cushioning material to wedge the display inside the controller grip of the clear back plate.

Follow the PhobGCC-SW RP2040 build guide for building the firmware. The firmware can be found in rp2040/build/phobgcc_rp2040.uf2

## Display Usage
* (D-pad Left) Time Tracking: display how long you have been connected to a setup in hr:mn:sc format
* (D-pad Down) IPM Tracking: display live IPM averaged over a 10-second interval of play
* (D-pad Right) OWO: display an "owo" face that tells you good luck when pressing start :)
* (Z + D-pad Down) Boot Text: display the kiteTRAK boot text
* (Z + D-pad Right) Invert Display: invert the entire display, applies for all modes
* (Z + Start) Turn off the display (if display is inverted, it will show an all white display when shut off)
