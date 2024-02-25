---
title: Configure RF Module Type
keywords: reset, factory, default, security
last_updated: Feb 25, 2024
tags:
summary: "This page describes how to reset your device back to default settings"
sidebar: mydoc_sidebar
permalink: configure-a-rf-module-type.html
folder: mydoc
---

### Background

There are two main types of RF Modules:
1. Base Station - Connects to an micro-controller (MCU), like a Raspberry Pi , Arduino or BeagleBone) and acts as the collection point for all incoming and outgoing messages to/from the Sensor Nodes
2. Sensor node - A sensor node is and end point sensor that is usually collecting sensor reading and sending them back top the base station. The sensor node often battery powered and most of the time sleeps in between sending readings.

{% include image.html file="Slide1.jpg" alt="Big Picture"%}

The type of the RF Module determines some behavioral characteristics of the device:
1. An RF Module configured as base station (TYPE2) will have the serial port enabled and must be connected to the serial port of a micro-controller, and must have a dedicated power supply. You cannot make a TYPE2 module sleep. The Raspberry Pi Base Station is an example of a TYPE2 module.
2. An RF Module configured as sensor node does not have the ability to use the serial port and can be made to sleep in between sensor reading transmissions.
There are multiple TYPE configurations (e.g. TYPE1, TYPE3, TYPE4 ...). Refer the [Wireless Sensor Manual](https://cdn.shopify.com/s/files/1/0019/4065/2092/files/Wireless_Sensor_User_Manual_v0.5_1.pdf?118055261621237787) Message Reference for more details on the supported sensor node types.

The TYPE is a software configuration and can be be changed using the TYPE command. When you change the type it will take on the characteristics described in the above two points.

### Tutorial

In this tutorial you will change a sensor node (TYPE1) to a base station (TYPE2), and then change it back to a sensor node.

* What you will need:
- Knowledge on how to [communicate with RF Modules](https://projects.privateeyepi.com/home/home-alarm-system-project/wireless-projects/wireless-sensor---flex-rf-module/flex-tutorials/establish-communications.php)
- A base station
- A sensor node that is awake. Refer this tutorial for how to wake up a sleeping sensor node.

Step 1: Send the command to the sensor to change the its TYPE to TYPE2.

python rf_config.py 45 TYPE2
sending     : a45TYPE2
response is : a45TYPE2----

Step 2: Restart the sensor

Either power off and back on, or send it a REBOOT command

python rf_config.py 45 REBOOT
sending     : a45REBOOT
response is : a45REBOOT---

The sensor node is now configured as a base station and can be connected to a micro-controller. We have another tutorial that shows you how to physically connect RF modules to a Raspberry Pi.

You can set the RF module back to being a TYPE sensor by sending typing the following command:

python rf_config.py 45 TYPE1
sending     : a45TYPE1
response is : a45TYPE1----

python rf_config.py 45 REBOOT
sending     : a45REBOOT
response is : a45REBOOT---
