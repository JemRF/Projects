---
title: Wake & Sleep
keywords: Wake & Sleep, factory, default, security
last_updated: Sep 28, 2020
tags:
summary: "This page describes how to reset your device back to default settings"
sidebar: mydoc_sidebar
permalink: wake-sleep.html
folder: mydoc
---
Sleep background

Sensor nodes have the ability to sleep in order to save battery power. A sensor node uses very little battery power when asleep (0.5ua) which can significantly extend the battery lifetime of a sensor. When asleep the device will wake up either by an external switch or an internal timer.

You can set a timed interval between 1 and 999 minutes that will awaken the sensor every X minutes. When the timer reaches the threshold then it will awaken, send a reading, reset the timer, and and go back to sleep. This is called a cyclic sleep and can be activated using the CYCLE command. The RF modules support a multitude of external sensors. The TYPE of the sensor determines which sensor reading is transmitted in the cycle. For example a TYPE1 sensor will send a thermistor reading, TYPE3 will send a temperature and humidity reading from the DHT22 sensor etc.. For a full list of supported sensors and their associated types refer the [Wireless Sensor Manual](https://cdn.shopify.com/s/files/1/0019/4065/2092/files/Wireless_Sensor_User_Manual_v0.5_1.pdf?118055261621237787).

If you want the RF module to be awaken by switching the external switch (e.g. alarm door switch) then you put the device to sleep using the SLEEP command. The device will awaken every time the switch change state (e.g. door open or close), send a reading, and go back to sleep. You can also configure the device to send the a switch state (e.g. door is open) based on the interval. This way you will get a new reading every time the door opens and closes and you will also get the door status every X minutes.

* Awake background

When a device goes to sleep it shuts down the radio and only powers the timer or monitors for a switch change. Therefore once asleep the device will no longer process incoming radio messages. However you can wake the device by sending it the WAKE command within the first 5 seconds of it being started up.

* Tutorial

In this tutorial you will learn how to wake up a sensor node and put it back to sleep using both sleep methods (CYCLE and SLEEP).

1. Configure a cyclic sleep (send a thermistor reading every 5 minutes).

-Step 1 : Set the interval to 5. Make sure you use an three digit interval setting ("005" is good, "5" is bad)

python rf_config.py 45 INTVL005
sending     : a45INTVL005
response is : a45INTVL005-
-Step 2 : You can configure the amount of messages you want to be sent every time the device awakens. For this tutorial we will set this configuration to one (i.e. one message every 5 minutes).

python rf_config.py 45 NOMSG1
sending     : a45NOMSG1
response is : a45NOMSG1---

-Step 3 : Put the device into a cyclic sleep

python rf_config.py 45 CYCLE
sending     : a45CYCLE
response is : a45CYCLE----a45TMPA17.42a45SLEEPING-
Notice the device responded with three messages:

message acknowledgement (a45CYCLE----)
one temperature reading (a45TMPA17.42)
message indicating the device is going to sleep (a45SLEEPING-)
The device is now asleep and will no longer respond to your commands. Test this by sending it a HELLO message. You should see no response.

python rf_config.py 45 HELLO
sending : a45HELLO
sending : a45HELLO
sending : a45HELLO

You can check that you are receiving a reading every 5 minutes by running the serial monitor and watching for messages being transmitted. Below is an example of a sensor waking up, sending a reading and then going back to sleep.

python serial_mon.py 9600
To exit press ESC
Sun Feb 25 23:52:52 2018 a01HELLO----
Sun Feb 25 23:53:50 2018 a45AWAKE----
Sun Feb 25 23:53:50 2018 a45TMPA17.42
Sun Feb 25 23:53:50 2018 a45SLEEPING-


2. Wake up a sleeping Sensor Node

In order to wake up a sleeping sensor node you need to send it the WAKE command within the first 5 seconds of it being started up. The device takes a second to start and sends the 5 STARTED messages so in reality you should send the WAKE command one second after starting up the sensor.

- Step 1 : Type out the WAKE command but don't hit enter just yet

Note : On earlier versions of the WAKE command was AWAKE not WAKE. If you have an earlier version you might need to use the AWAKE command.

python rf_config.py 45 WAKE

- Step 2 : Power off and power up the Sensor Node, wait a second
- Step 3 : Send the awake command (hit enter)

python rf_config.py 45 WAKE
sending     : a45WAKE
response is : a45WAKE-----

The device is now awake and you can once again send it messages. You may need to try it a few times to get the timing right.

Note : When the device is asleep and being powered by a battery and you remove the battery power and re-connect it may not always restart. The reason for this is the device has an internal capacitor that can keep the device running without power for some time.  You can discharge the capacitor by grounding the device. Usually touching the GND with your fingers is enough to discharge it (don't worry it won't shock you). You won't have this problem when using an external power supply because the power supply is grounded.

3. Configure a sleep (send a switch reading every time a switch is triggered and send switch state every 1 minute).

- Step 1 : Set interval to 001

python rf_config.py 45 INTVL001
sending     : a45INTVL001
response is : a45INTVL001-

- Step 2 : Put the device to sleep

python rf_config.py 45 SLEEP
sending     : a45SLEEP
response is : a45STATEOFF-a45SLEEPING-

- Step 3 : Run serial_mon to monitor switching events

For the below test I closed and opened an external door switch attached to the sensor.

python serial_mon.py 9600
To exit press ESC
Mon Feb 26 00:16:06 2018 a01HELLO----
Mon Feb 26 00:16:22 2018 a45AWAKE----
Mon Feb 26 00:16:22 2018 a45BUTTONON-
Mon Feb 26 00:16:22 2018 a45SLEEPING-
Mon Feb 26 00:16:23 2018 a45AWAKE----
Mon Feb 26 00:16:23 2018 a45BUTTONOFF
Mon Feb 26 00:16:24 2018 a45SLEEPING-


And because we set the interval to 001 we you will also see a switch state message every minute as shown below:

Mon Feb 26 00:20:01 2018 a45AWAKE----
Mon Feb 26 00:20:01 2018 a45STATEOFF-
Mon Feb 26 00:20:01 2018 a45SLEEPING-
