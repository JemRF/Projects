---
title: Change the Device ID
keywords: reset, factory, default, security
last_updated: Feb 25, 2024
tags:
summary: "This page describes how to Change the Device ID"
sidebar: mydoc_sidebar
permalink: change-the-device-id.html
folder: mydoc
---
n this tutorial you will change the Device ID of a RF module. The Device ID is what uniquely identifies each module on a Personal Area Network (PAN).  The PanID is a 5 digit numeric identifier (00000-99999). As shown in the below diagram the PanID is used to group RF Modules (including base stations).


{% include image.html file="Slide2.jpg" alt="Big Picture"%}


The Device ID is two character identifier. You can change the Device ID of any RF module using the CHDEVID command. The PrivateEyePi server requires a numeric ID (like 89), but you can change the ID using any characters (like AB) from 34-122 on the ASCII table (basically most of the letters on a keyboard).

Theoretically this allows you to have 7,744 unique identifiers for a sensor, but only 100 with PrivateEyePi on each PAN.

You can also use frequencies and channels to further diversify your network, if required. Each device supports 6 frequencies, 10 channels per frequency, 99,999 PAN's per channel, and 7,744 Device ID's per PAN. Theoretically this design supports 16M devices in a given area.

What you will need:
* A Raspberry Pi (or suitable MCU like Arduino or BeagleBone) connected to a [base station receiver](https://www.jemrf.com/collections/rf-sensors/products/wireless-base-station-for-raspberry-pi)
* A [sensor node](https://www.jemrf.com/collections/rf-sensors) (wireless sensor or Flex)

Step 1 : Open a terminal session on the Raspberry Pi and [establish connectivity](https://projects.privateeyepi.com/home/home-alarm-system-project/wireless-projects/wireless-sensor---flex-rf-module/flex-tutorials/establish-communications.php) with the device on which you wish to change the DeviceID. Type the following command:

python rf_config.py 03 HELLO

Watch for the following response:

sending     : a03HELLO
response is : a03HELLO----

You don't always need to do this step. You could start with step 2, but its a good idea to check if the device you are wanting to configure is up and running and accepting and responding to commands.

Step 2 : Use the CHDEVID command to change the device ID

In  this example I will change the Device with Device ID of 03 to 45.

python rf_config.py 03 CHDEVID45
sending     : a03CHDEVID45
response is : a03CHDEVID45

The fact that you received "a03CHDEVID45" as a response means that the change was successful. You can now test if the device is responding to the new ID by sending a HELLO message to the new Device ID.

python rf_config.py 45 HELLO
sending     : a45HELLO
response is : a45HELLO----

In above examples we changed the Device ID over the air, but you could also use the same commands over the serial port of a device. Note that in order to communicate with a device over the serial port the device must be a Type 2 sensor. Refer xyz tutorial on Sensor Types.

You can view the video tutorial here (maximize screen to be able to read the text):

https://youtu.be/eZpDi8QuWDk
{% include youtubePlayer.html id=page.eZpDi8QuWDk %}