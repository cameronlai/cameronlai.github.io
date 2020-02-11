---
title:  "Zemote Beta"
last_modified_at: 2015-03-15T16:15:00+08:00

---
Program Zemote with your own remote control You can configure Zemote into any kind of remote control. The best thing about Zemote is that you can program a button to do multiple things. For example, you can configure the power button to power the television, air conditioner and sound system in one go. 

![alt text](http://cameronlai.com/wp-content/uploads/2015/07/zemote-beta-prototype-300x215.jpg)
*Zemote beta prototype*

![alt text](http://cameronlai.com/wp-content/uploads/2015/07/zemote-beta-prototype.jpg) 
*Zemote beta prototype*

![alt text](http://cameronlai.com/wp-content/uploads/2015/07/inside-zemote-beta-prototype-300x248.jpg)
*Inside Zemote beta prototype*

### Basics

The Zemote Shield inlcudes 6 buttons.

1.  Power
2.  Volume +
3.  Volume -
4.  Channel +
5.  Channel -
6.  Home

Zemote programming supports 2 programming modes

1.  TV Mode
    * Home button will lead you to the channel 1 commands
    * Channel + and Channel - buttons will iterate through all channel commands.
2.  Simple Mode
    * Home button will execute channel 1 commands
    * Channel + button will execute channel 2 commands
    * Channel - button will execute channel 3 commands

There are a few constraints in the Zemote set up and they are shown below.

1.  Maximum number of channels is 6
2.  Maximum number of command per channel or button is 8

### Zemote Host

[Zemote Host Release](https://github.com/cameronlai/ZemoteHost/releases)

[Zemote Host Source Code](https://github.com/cameronlai/ZemoteHost)

Zemote Host allows you to connect to your Zemote device seamlessly. It helps you visualize the whole IR programming progress by showing you the IR codes through the terminal on the right hand side. The software is written in Python, using wxPython as the user interface engine. The latest version is 2015.XX.XX and if you have any feedback, please let me know or add an issue on [github](https://github.com/cameronlai/ZemoteHost).

![alt text](http://cameronlai.com/wp-content/uploads/2015/03/zemote-host-screenshot.jpg)
 *Zemote Host Screenshot*

### Zemote Firmware

[Zemote Firmware Release](https://github.com/cameronlai/ZemoteFirmware/releases)

[Source Code](https://github.com/cameronlai/ZemoteFirmware)

Zemote Firmware Source Code\[/standout-css3-button\] Zemote Firmware is a piece of code that can communicate to Zemote Host and it also handles all the button handling. When a button is pressed on Zemote, Zemote Firmware will run through the saved sequence and this means you can do more through one remote control button. The firmware is written in Arduino as Arduino is easy and fun to use. The latest version is 2015.XX.XX and if you have any feedback, please let me know or add an issue on [github](https://github.com/cameronlai/ZemoteFirmware).

### Zemote Shield


[Zemote Sheild Release](https://github.com/cameronlai/ZemoteShield/releases)

[Zemote Shield Source Files](https://github.com/cameronlai/ZemoteShield)

Zemote Shield is built as a shield for Arduino Uno or Arduino Nano. Nano has a smaller footprint and should be preferred. The latest version is Rev. A and if you have any feedback, please let me know or add an issue on [github](https://github.com/cameronlai/ZemoteShield). 

![alt text](http://cameronlai.com/wp-content/uploads/2015/07/zemoteshield-rev-a-schematics.png) 
*Zemote Shield Rev A Schematics*

### Summary

The whole project can demonstrates the idea of a programmable remote control. However, there are still many improvements to be made before it can be realized completely. For example, the power consumption is still much greater than a commercial remote control and this must be improved. Maybe one day I'll revisit the project and redesign different parts to make it more user-friendly. For now, at least it work! :)