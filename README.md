# SparkFun Arduino Boards w/ XInput
[![Build Status](https://github.com/dmadison/ArduinoXInput_Sparkfun/workflows/build/badge.svg?branch=master)](https://github.com/dmadison/ArduinoXInput_Sparkfun/actions?query=workflow%3Abuild)

This repository contains support for the SparkFun Arduino-compatible development boards, modified to work as XInput devices. Originally forked from [the SparkFun repo](https://github.com/sparkfun/Arduino_Boards).

These boards are meant to be used in conjunction with the [ArduinoXInput library](https://github.com/dmadison/ArduinoXInput).

## Installation
<pre>
└───Arduino Installation
	├───drivers
	├───examples
	├───hardware
	│   ├───arduino
	│   ├───tools
	│   ├───<b>xinput</b>
	│   └───<b>xinput_sparkfun
	│       └───avr
	│           ├───bootloaders
	│           ├───cores
	│           ├───libraries
	│           └───variants</b>
	├───java
	├───lib
	├───libraries
	├───reference
	├───tools
	└───tools-builder
</pre>

To install, you first need to install the latest version of the Arduino XInput AVR Core, [which can be found here](https://github.com/dmadison/ArduinoXInput_AVR). Follow [the installation instructions](https://github.com/dmadison/ArduinoXInput_AVR/#installation) provided in that repository and verify that those boards are installed correctly before proceeding.

This boards package uses the same process for installation. Download [the latest version](../../releases/latest) of this repository to your PC. Navigate to the directory containing your Arduino installation, and then open up the 'hardware' folder. Extract the contents of the .zip file into this directory. You should have a new 'xinput_sparkfun' folder with an 'avr' folder inside of it, containing the files from this repository (see the tree view above).

Restart the Arduino IDE. If the SparkFun boards are installed correctly, you should see a new collection of "SparkFun AVR Boards w/ XInput" in the `Tools -> Boards` menu.

To uninstall, delete the 'xinput_sparkfun' folder in the 'hardware' directory, and then restart the Arduino IDE.

## Upload Warning and Instructions

Due to the nature of how the XInput USB mode works, Arduinos that have XInput sketches on them will ***not*** automatically reset when programmed by the IDE! You will need to reset the board by hand every time you upload new code.

[Full instructions for uploading are provided in the AVR Core repository](https://github.com/dmadison/ArduinoXInput_AVR/#upload-warning-and-instructions).

**Do *not* upload XInput sketches to your Arduino unless you know how to reset it!** Otherwise you will not be able to program it anymore and you'll have to remove the XInput sketch by flashing the board with an external programmer.

## Included Boards

All of the following boards make use of the [Arduino XInput AVR core](https://github.com/dmadison/ArduinoXInput_AVR):

* [MaKey MaKey](https://www.sparkfun.com/products/11511)
* [Pro Micro 3.3V](https://www.sparkfun.com/products/10999)
* [Pro Micro 5V](https://www.sparkfun.com/products/11098)
* [Fio v3](https://www.sparkfun.com/products/11520)
* [Qduino Mini](https://www.sparkfun.com/products/13614)
* [LilyPad USB Plus](https://www.sparkfun.com/products/14346)

Other SparkFun boards may be theoretically compatible with XInput, but are not yet available because the XInput USB modifications have not been ported to their architecture.
