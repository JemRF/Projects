---
title: "PrivateEyePi"
keywords: getting started introduction
last_updated: Jan 30, 2024
tags:
summary: This is a Raspberry Pi projects website aimed at the Raspberry Pi enthusiast wanting to build home security/automation systems and at the same time learn programming and electronics.
All software and source code we provide is free of charge can be copied, shared and modified without restriction. There are no charges for the alarm system or any of the projects. The parts you will need are described in the projects and can be sourced on your own or bought from the PrivateEyePi Store .
sidebar: mydoc_sidebar
permalink: index.html
folder: mydoc
---
## Home Automation and Monitoring Projects for Raspberry Pi
{% include image.html file="PrivateEyePi Main Page (640x491).jpg" alt="PrivateEyePi Monitoring"%}
## Welcome to Pi Projects by JemRF, aka: PrivateEyePi
While this is primarily a **Raspberry Pi** projects website aimed at the Raspberry Pi enthusiast wanting to build home security/automation systems and at the same time learn programming and electronics. But we are not limited to Raspberry Pi, we also support many of the **Orange Pi** boards as well. For details visit [Using Orange Pi with JemRF products](https://jemrf.github.io/RF-Documentation/orangepi.html) . We also include our WiFi IoT product line as it is both standalone or server connected and has features you to customize.

Our goal is to stimulate interest in home and DIY electronics that could lead to great projects or new career opportunities. We want to help those interested in learning electronics with working examples from how to make a temperature sensor, to how to build a home alarm system.
All software and source code we provide is free of charge can be copied, shared and modified without restriction. There are no charges for the alarm system or any of the projects. The parts you will need are described in the projects and can be sourced on your own or bought from the [JemRF Store](https://wwww.jemrf.com).

There are two free servers, one for the DIY minded at PrivateEyePi.com for you can use to monitor events, temperatures, and other types of sensors. The second is for a more professional looking monitoring dashboard there is [monitor.jemrf.com](https://monitor.jemrf.com) with free notification.

<!-- no toc -->
## The Internet Of Things (IoT) (with RaspberryPi and RF Devices)
Using your Raspberry Pi you can easily build your own sensors and make your own Internet of Things (IoT).

## Build Sensors
We have many tutorials that show you how to build sensors, or you can build them using hundreds of online tutorials. Some of our sensor tutorials include :

[Door switch/Reed switch](https://projects.privateeyepi.com/home/home-alarm-system-project.php), [Motion Sensor](https://projects.privateeyepi.com/home/home-alarm-system-project.php), [Temperature Sensor](https://projects.privateeyepi.com/home/temperature-sensor-project-using-ds18b20.php), [Humidity Sensor](https://projects.privateeyepi.com/home/home-alarm-system-project/temperature-and-humidity.php), [Web Cam Motion Sensor](https://projects.privateeyepi.com/home/webcam-surveillance-project.php), [Water Sensor](https://projects.privateeyepi.com/home/home-alarm-system-project/wireless-projects/flood-water-presence-sensor.php).

Using our [range of wireless tutorials](https://projects.privateeyepi.com/home/home-alarm-system-project/wireless-projects.php) you can convert your sensor to a wireless battery operated IOT device!

## Connect Your Sensor to The Internet

In each of our projects we show you how to, firstly, build the sensor and secondly connect it to The Internet using your Raspberry Pi. We supply the Python code that you download from our web server.

## Create an Alarm System

PrivateEyePi has a [cloud based alarm system](https://projects.privateeyepi.com/home/home-alarm-system-project.php) where you can group sensors using zones. Zones can be activated and alarms triggered based on rules that you define.

## Control Relays

Some sensors, like relay switches, can be controlled through The Internet. You can also control the alarm system through the PrivateEyePi web based dashboard.

## Monitor

Using our [dashboard](https://projects.privateeyepi.com/home/home-alarm-system-project/installation/how-it-works.php) you can monitor the status of sensors and view temperature and humidity readings in real time from The Internet. Using the PrivateEyePi Analytics you can view historical information. You can see trends using our daily, hourly and detailed data views.

## Trigger

IOT devices are useful for triggering alerts. Using our [sophisticated rules engine](https://projects.privateeyepi.com/home/rules-1.php) you can create rules that are processed in real time to create alerts tailored to your needs. You use parameters like sensor values, time of day, days of week, alarm activated/deactivated to define rules specific to individual sensors. The rules can alert you to specific events like a door being opened, motion being detected or temperature or humidity reaching a threshold. You can also use the rules to determine if something hasn't happened. For example you may want to know if no motion has been detected for a time period (popular for monitoring the elderly). Or you may want to know if your garage door was not closed. You can also apply a delay setting to a rule that will only trigger after the rule if valid for a period of time (e.g. garage door open for more than 5 minutes). This is also useful for monitoring the temperature of your house or a fridge where you only want to be alerted after a sustained temperature drop or increase.


## The Internet Of Things (IOT) WiFi Devices
The [Internet Of Things WiFi sensors](https://documents.jemrf.com/wifi_iot.html) make connecting to The Internet easier than ever. You don't need no be an electronics or software expert or spend a lot of money on proprietary and closed systems to create your own IOT devices. The WiFi IOT Sensor can be controlled and monitored from The Internet.

## Projects:
### [Home Alarm System Project](https://projects.privateeyepi.com/home/home-alarm-system-project.php)
* Build a home alarm system and link it to existing door contacts or alarm sensors
* Connect the alarm system to our server which will feed your own personal WWW dashboard, which is designed for mobile devices
* Use the dashboard to control your alarm system zones, and view alerts and activity logs
* Configure your Raspberry Pi to send email alerts to you whenever a alarm occurs
* Receive alerts and view your dashboard from you PC, smart phone or any device that has a browser and connection to the internet
### [Webcam Surveillance Projects](https://projects.privateeyepi.com/home/webcam-surveillance-project.php)
* Create a surveillance monitor using any popular webcam and a Raspberry Pi
* Create a motion sensor from a webcam and a Raspberry Pi
* Create email alerts with pictures attached when motion is detected.
### [Multiple Temperature Gauges On One Dashboard](https://projects.privateeyepi.com/home/temperature-sensor-project-using-ds18b20.php)
* Build a digital temperature gauge with the highly accurate DS18B20 or DHT22 sensor
* Display a temperature gauge and graph in Celsius (centigrade) or Fahrenheit on your dashboard
* Add as many temperature gauges as you like to your dashboard
#### [DS18B20 Temperature Project](https://projects.privateeyepi.com/home/temperature-sensor-project-using-ds18b20.php)
* Multiple DS18B20 sensors can be connected to the same GPIO pin
* Does not support humidity
#### [DHT22 Project](https://projects.privateeyepi.com/home/home-alarm-system-project/temperature-and-humidity.php)
* Multiple DHT22 sensors can be connected to multiple GPIO pins
* DHT22 does support humidity which is also displayed on the dashboard

{% include image.html file="raspberry pi multiple temperature sensor dashboard6708.png" alt="DHT22 Project"%}

### [Wireless Sensor Projects](https://projects.privateeyepi.com/home/home-alarm-system-project/wireless-projects.php)
* Build a wireless temperature sensor, wireless door contact or panic button, wireless water sensor or wireless motion sensor.
* We have sourced high reliable wireless components that have very long battery life (over 1 million transmits from 1 battery) and very powerful radio frequency signal that can easily operate in and around your home.
* Highly secure encrypted communication
* No knowledge in wireless communications necessary the wireless modules communicate with each other using a light weight easy to understand text protocol (LLAP)
* Lowest price point on the market for this sophistication
* Visit the [RF Devices store](https://www.jemrf.com) to purchase the components

{% include image.html file="IMG_49756ed6.jpg" alt="Wireless Temperature Sensor"%}

Wireless Temperature Sensor

### [Water sensing project (wired to Raspberry Pi)](https://projects.privateeyepi.com/home/home-alarm-system-project/wireless-projects/flood-water-presence-sensor.php)

<div class="sites-embed-content sites-embed-type-youtube"><iframe title="YouTube video player" class="youtube-player" type="text/html" src="https://www.youtube.com/embed/FjUaJhQ2Rzc?rel=0&amp;wmode=opaque" frameborder="0" allowFullScreen="true" width="480" height="270"></iframe></div>


### [Siren Project](https://projects.privateeyepi.com/home/home-alarm-system-project/siren-project.php)
* Attach a buzzer or external siren to the alarm system
* This project is dependent on you completing the alarm system project first
### [Arm/Disarm using a switch](https://projects.privateeyepi.com/home/home-alarm-system-project/arm-disarm-using-a-switch.php)
* Arm/Disarm your alarm using switches connected to your Raspberry Pi
### [Automate your alarm and sensors](https://projects.privateeyepi.com/automate-your-alarm.php)
* Auto restart the alarm if it is down
* Run the alarm as a background process

### [On/Off Project](https://projects.privateeyepi.com/home/on-off-project.php)
* Switch a light on/off using your smart phone
* Utilizes a relay switch, GPIO ports, a light weight web server and JavaScipt running on Node.js
* Everything runs locally on your Raspberry Pi
* No programming skills required
{% include image.html file="IMG_4524 (640x480)1cd9.jpg" alt="ON/Off Project"%}

