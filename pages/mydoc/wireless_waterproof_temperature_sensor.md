---
title: Wireless Waterproof Temperature Sensor
keywords: wireless temperature, temperature, sensor, 10k, thermistor, waterproof
last_updated: Sep 28, 2020
tags:  
summary: "This page explains the JEMRF Wireless Waterproof Temperature Sensor"
sidebar: mydoc_sidebar
permalink: wireless_waterproof_temperature_sensor.html
folder: mydoc
---

{% include image.html file="IMG_6681_1024_small.jpg" alt="Wireless Waterproof Temperature Sensor"%}

## Product Description
Wireless waterproof temperature sensor with accuracy of ~1°C accuracy. The sensor is on 3 feet of wire. Wire and sensor are waterproof. The RF Module in the cream case is not waterproof. Very low power and can last up to a year on a single CR2032 coin cell battery when configured to send readings every 10 minutes. 

## Installation
Install battery and close enclosure as described [here](sensor_installation.html).

## Sensor testing
* See the [testing section](sensor_testing.html) of this documentation 

## Product Specifications
* ~1°C accuracy
* 10K (NTCLE100E3103JB0) thermistor sensor
* [Device specifications](rf_device_specs.html)

### Electrical
* 2.2-3.3V 
* Powered by CR2032 coin cell battery
* Can be externally powered by soldering to the 3V3 and GND through holes on the PCB

### Functional
* Standard JemRF wireless sensor, refer [RF Communications section](rf_basics.html) for all the details
* [Highly configurable](configuration_overview.html)

### Messaging details
* TMPA99.99 (temperature reading format)
* TEMP (the TEMP command requests the sensor to transmit a temperature reading)

### Physical
* 36mm x 36mm x 15mm case size (1.42" x 1.42" x .59")

## Default configuration
* Type 1 ([Type](types.html) 1 sensor)
* NOMSG1 (Sends 1 temperature reading every cycle)
* INTVL005 (Sends a temperature reading every 5 minutes)
* CYCLE (put the device into a [timed sleep cycle](sleep_modes.html))
* Refer [device configuration](configuration_overview.html) for more details

{% include note.html content="Did you know this sensor is also a [multi function sensor](multi function sensors.html)?"%}