# Zumo32U4 library

Version: 1.2.0<br/>
Release date: 2020-09-11<br/>
[![Build Status](https://travis-ci.org/pololu/zumo-32u4-arduino-library.svg?branch=master)](https://travis-ci.org/pololu/zumo-32u4-arduino-library)<br/>
[www.pololu.com](http://www.pololu.com/)

## Summary

This is a C++ library for the Arduino IDE that helps access the on-board hardware of the Zumo 32U4 robot.

The user's guide for the Zumo 32U4 robot is here:

https://www.pololu.com/docs/0J63


## Installing the library

1. Download the [library from here](https://github.com/Alexanderallenbrown/Zumo32U4/archive/refs/heads/main.zip) and decompress it.
2. Rename the folder "zumo-32u4-arduino-library-master" to "Zumo32U4".
3. Move the "Zumo32U4" folder into the "libraries" directory inside your Arduino sketchbook directory.  You can view your sketchbook location by opening the "File" menu and selecting "Preferences" in the Arduino IDE.  If there is not already a "libraries" folder in that location, you should make the folder yourself.
4. After installing the library, restart the Arduino IDE.

## Examples

Several example sketches are available that show how to use the library.  You can access them from the Arduino IDE by opening the "File" menu, selecting "Examples", and then selecting "Zumo32U4".  If you cannot find these examples, the library was probably installed incorrectly and you should retry the installation instructions above.

## Classes and functions

The main classes and functions provided by the library are listed below:

* Zumo32U4ButtonA
* Zumo32U4ButtonB
* Zumo32U4ButtonC
* Zumo32U4Buzzer
* Zumo32U4Encoders
* Zumo32U4IMU
* Zumo32U4IRPulses
* Zumo32U4LCD
* Zumo32U4LineSensors
* Zumo32U4Motors
* Zumo32U4ProximitySensors
* ledRed()
* ledGreen()
* ledYellow()
* usbPowerPresent()
* readBatteryMillivolts()

## Component libraries

This library also includes copies of several other Arduino libraries inside it which are used to help implement the classes and functions above.

* [FastGPIO](https://github.com/pololu/fastgpio-arduino)
* [PololuBuzzer](https://github.com/pololu/pololu-buzzer-arduino)
* [PololuHD44780](https://github.com/pololu/pololu-hd44780-arduino)
* [Pushbutton](https://github.com/pololu/pushbutton-arduino)
* [QTRSensors](https://github.com/pololu/qtr-sensors-arduino)
* [USBPause](https://github.com/pololu/usb-pause-arduino)

You can use these libraries in your sketch automatically without any extra installation steps and without needing to add any extra `#include` lines to your sketch.

You should avoid adding extra `#include` lines such as `#include <Pushbutton.h>` because then the Arduino IDE might try to use the standalone Pushbutton library (if you previously installed it), and it would conflict with the copy of the Pushbutton code included in this library.  The only `#include` lines needed to access all features of this library are:

~~~{.cpp}
#include <Wire.h>
#include <Zumo32U4.h>
~~~

## Version history

* 1.2.0 (2020-09-11): Added a Zumo32U4IMU class that abstracts some details of the inertial sensors and supports different IMU types. The examples have been updated to use this class.
* 1.1.4 (2017-07-17): Fixed a bug that caused errors from the right encoder to be reported as errors from the left encoder.
* 1.1.3 (2016-10-12): Fixed a bug that caused the buzzer's `isPlaying` method to malfunction sometimes when link time optimization is enabled.  Also incorporated some minor fixes to the QTRSensors and LSM303 libraries.
* 1.1.2 (2016-03-14): Updated the Demo example so it can compile in Arduino 1.6.7.
* 1.1.1 (2015-09-01): Moved the library out of the a-star repository into its own repository. Added Demo example.
* 1.1.0 (2015-05-06): Updated FastGPIO to version 1.0.2.  Fixed a bug in Zumo32U4ProximitySensors where the wrong array length was used.  Added five demos: RotationResist, FaceUphill, RemoteControl, Balancing, and SumoProximitySensors.
* 1.0.1 (2015-03-11): Improve the Buttons example.
* 1.0.0 (2015-03-05): Original release.
