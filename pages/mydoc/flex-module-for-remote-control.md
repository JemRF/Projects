---
title: how-to-use-the-flex-module-for-remote-control
keywords: reset, factory, default, security
last_updated: Feb 25, 2024
tags:
summary: "This page describes how-to-use-the-flex-module-for-remote-control"
sidebar: mydoc_sidebar
permalink: flex-module-for-remote-control.html
folder: mydoc
---

How to use the FLEX Module for Remote Control

<img src="images/flex_led_demo.jpg" width="425"/>


The FLEX RF module has 5 IO pins that can be independently switched on/off (high low) over the air.

The five IO pins are pins:

Pins 3,4, and 5 are switched using the GPIO command
Pins 15 and 16 are switched using the RELAY command.
<img src="images/flex pinout.png" width="425"/>

All 5 pins act in same way. The command RELAYON or GPIO1 will switch the pin high (2-3.3V) and RELAYOFF and GPIO0 will switch the pin low (0V).The high voltage level depends on the input current to the RF module. The input current range for the FLEX module is 2V to 3.3V.


Important!

Configure the FLEX module as Type 7 to enable control of the relay and GPIO pins. Do this using the TYPE command.

E.g. a03TYPE7 (and reboot)

See here for more detail on how to change a device's type.

Here are some examples:

Use a FLEX module to switch an LED

As shown in Figure 1 you can connect LED lights to each of the five IO pins that can be independently switched using the GPIO and RELAY commands.


<img src="images/FLEX Relay Direct" width="425"/>


Figure 1 - Wiring diagram for a FLEX and LED


Alternatively you can use the FLEX module to switch an external circuit. You can do this using a transistor. The diagram shown in Figure 2 shows an external LED circuit with it's own power source that is switched on/off using a NPN2222a transistor based on input from the FLEX module.


<img src="images/FLEX LED Transistor.png" width="425"/>


Figure 2 - Wiring diagram for a FLEX switching an external circuit



Use a FLEX module to switch a relay

A relay takes an input trigger and switches a high voltage circuit (e.g. 110V or 240V) based on whether the input is high or low. The FLEX module will output a voltage level the same as its input (2V to 3.6V), however the current that it delivers may not be enough to trigger some relay switches. You can connect the FLEX module directly to the relay input as shown in Figure 3, or if the current is not strong enough to trigger the relay then use the circuit in Figure 4.


<img src="images/FLEX Relay Direct.png" width="425"/>


Figure 3 - Wiring diagram for FLEX and a relay


<img src="images/FLEX Relay External.png" width="425"/>


Figure 4 - Wiring diagram for FLEX using a transistor to trigger the relay

Note: In order to use the relay status command RELAYA or RELAYB we suggest adding a 1k-10k resistor between the Flex module and the "B" leg of the transistor. Without the resistor you may receive incorrect status values.



See also how to configure PrivateEyePi Rules to control a FLEX module remotely.
See all other FLEX tutorial here.
```

