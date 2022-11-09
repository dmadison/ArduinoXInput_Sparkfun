# SparkFun Arduino Boards w/ XInput
[![Build Status](https://github.com/dmadison/ArduinoXInput_Sparkfun/workflows/build/badge.svg?branch=master)](https://github.com/dmadison/ArduinoXInput_Sparkfun/actions?query=workflow%3Abuild)

This repository contains support for the SparkFun Arduino-compatible development boards, modified to work as XInput devices. Originally forked from [the SparkFun repo](https://github.com/sparkfun/Arduino_Boards).

These boards are meant to be used in conjunction with the [ArduinoXInput library](https://github.com/dmadison/ArduinoXInput).

## Automated Installation

Follow the official instructions for [adding third party boards](https://support.arduino.cc/hc/en-us/articles/360016466340-Add-or-remove-third-party-boards-in-Boards-Manager) and [adding boards to the Arduino IDE](https://support.arduino.cc/hc/en-us/articles/360016119519-Add-boards-to-Arduino-IDE).

Add the following line to the "Additional Boards Manager URLs" list:
```
https://raw.githubusercontent.com/dmadison/ArduinoXInput_Boards/master/package_dmadison_xinput_index.json
```

If you've done this correctly, the XInput boards packages will be available within the Boards Manager. Install the "XInput AVR Boards" package as well as the "XInput SparkFun Boards" package. Note that the core "XInput AVR Boards" package is required for the SparkFun boards to work.

## Manual Installation
<pre>
└───Arduino App Data Folder
    ├───cache
    ├───logs
    ├───staging
    └───packages
        ├───arduino
        └───<b>xinput</b>
        └───<b>xinput_sparkfun
            └───hardware
                └───avr
                    └───{version}
                        ├───bootloaders
                        ├───libraries
                        └───variants</b>
</pre>

To install manually you will need to find the Arduino IDE's application data folder. On Windows this is located in `%APPDATA%\..\Local\Arduino15`.

You will need to create the necessary folders in the "packages" directory: `xinput_sparkfun/hardware/avr/{version}`, where `{version}` is the current [semantic version number](https://en.wikipedia.org/wiki/Software_versioning) of the repository (e.g. "1.0.0"). The subfolder of this repository containing the boards files should then be copied into this folder. See the tree view above for reference.

You will also need to copy the boards files from the [Arduino XInput AVR core](https://github.com/dmadison/ArduinoXInput_AVR). Follow the instructions in the README. The two folders, `xinput` and `xinput_sparkfun`, should live next to each-other in the "packages" directory.

After you have copied the files, restart the Arduino IDE. If the SparkFun boards files are installed correctly, you should see a new collection of "SparkFun AVR Boards w/ XInput" in the `Tools -> Boards` menu. If you get an error while compiling, make sure the XInput AVR core is installed properly.

To uninstall, delete both "xinput" folders and then restart the Arduino IDE.

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
