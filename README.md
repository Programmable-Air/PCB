# PCB

PCB for Programmable-Air

The electronics for Programmable-Air are pretty simple, as these things go. The PCB is composed of two boards that are connected by default but can be snapped off and used independently. The 'master' board contains an Arduino Nano, two pumps and IO. The 'slave' board contains three valves and the pressure sensor circuit. In this way, the 'master' board contains the brains and IO as well as the pressure sources while the 'slave' board contains the valves to control air flow and feedback from the pressure sensor. The 'master' board contains connectors to attach two more slave boards, thus allowing you to control three independent soft robots with the same Arduino. However, most of the time you'd probably only use the boards in their default configuration.

Below is the pin definition for the v0.5 of the board:

![Programmable-Air PCB v0.5 Pin Definitions](https://github.com/Programmable-Air/PCB/blob/master/programmable-air-v0.5/pinDefinitions.png)

Here are the functions of all the Pins:

* Power:
	* __Vin(+12V)__ - from the external power source
	* __+5V__ - Regulated 5V from Arduino's linear 5V regulator
	* __GND__ - Common ground for all signals

* Onboard chips:
	* __D10__ - Drives the base of the transistor for Motor 1
	* __D11__ - Drives the base of the transistor for Motor 2
	* __D12__ - Drives the three onboard neopixels(for debugging and such)
	* __D13__ - Drives the base of the Load transistor. The collector of the Load is broken out as Load. You can connect it to an external pump or relay for regulating them.
	* __D2__ - Connected to the __blue__ button, pulled up using the internal 20K resistor and connects to ground when button is pressed
	* __D3__ - Connected to the __red__ button, pulled up using the internal 20K resistor and connects to ground when button is pressed
	* __AREF__ - Connected to a LM4040 +5V voltage reference

* Connections to slave boards
	* Board 0	 
		* __A3__ - Pressure sensor output(on the valve board). Can be used as a GPIO if slave board is not connected. Range~ 1V-4V
		* __D4__ - Drives Valve #02 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.
		* __D5__ - Drives Valve #01 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.
		* __D6__ - Drives Valve #00 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.

	* Board 1
		 * __A2__ - Pressure sensor output(on the valve board). Can be used as a GPIO if slave board is not connected. Range~ 1V-4V
		 * __D9__ - Drives Valve #12 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.
		 * __D8__ - Drives Valve #11 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.
		 * __D7__ - Drives Valve #10 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.

	* Board 2
 	 * __A5__ - Pressure sensor output(on the valve board). Can be used as a GPIO if slave board is not connected. Range~ 1V-4V
 	 * __A4__ - Drives Valve #22 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.
 	 * __A1__ - Drives Valve #21 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.
 	 * __A0__ - Drives Valve #20 via a transistor(on the valve board). Can be used as a GPIO if slave board is not connected.
