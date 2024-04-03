# Welcome to the Hive-Five Project ! 

## We will describe the implementation of our project on this GitHub.

# Introduction

Nowadays, the survival of 80% of flowering plants and the production of 35% of human food directly depend on pollinators.
In the 1990s, 10% of bee colonies were disappearing each year. Today, between 20 to 80% of bee colonies are disappearing each year.

There are increasing threats to bees:

- Varroa mite, an Parasitic mite, introduced in France since 1982.

- New insecticides, such as neonicotinoids, which affect the nervous system of insects and were introduced in the 1990s.

- Asian hornets introduced in France since 2006.

- Climate change, including extreme heat and drought.

- Increasing hive thefts in recent years for the honey business.

## Following these observations, we have decided to undertake a project : 

**Create a connected box that monitors the real-time status of a beehive for the beekeppers. It will check parameters such as temperature, humidity, and other metrics to determine if the hive is more or less productive.**

The project aims to develop a comprehensive embedded system, integrating sensors, a microcontroller, a communication module, and the necessary electronics for power management. The main objective is to provide real-time monitoring of the hive to optimize bee health and honey production. 

## Our first sessions involved understanding the project context by defining the project boundaries : 

For the Implementation: 

On the Hardware : we prototyped on a Labdec board followed by designing a printed circuit board (PCB). 
For the software : we needed to program the microcontroller and connect it to the Things Network

Software Resources Used:

◼ Electronic Design: KiCAD for designing printed circuit boards (PCB).

◼ Development Environment: Using the Arduino IDE for microcontroller programming.

Hardware Resources Used:

◼ Laboratory Equipment:  oscilloscope, power supply, function generator, and soldering station.

◼ Fabrication Tools: Using an engraver and equipped workshop with cable sheath, a heat gun, a filing machine.

◼ Basic Components: Utilization of electronic components such as resistors, essential for building the embedded system.

## Here is the list of components imposed by the project supervisors :

- MKR WAN 1310: Microcontroller board, LoRaWAN compatible, low power consumption, optimized for IoT projects.

- DHT22(x2): Environmental sensor providing precise measurement of temperature and humidity, with a wide operating range.

- DS18B20(x2): Waterproof thermal sensor, perfect for accurate measurements, featuring one-wire digital communication.

- HX711: Analog-to-digital converter for weight sensors, providing precise amplification and low power consumption.

- H401-C3: Force sensor with high load capacity, specially designed for weight monitoring in a hive.

- SOL3W: High-efficiency solar panel, resilient and durable, perfectly suited for commercial needs, promoting environmental sustainability.

## For the project we had : 
 High Level of Requirement:

❑ For hive weight: accuracy of 100 g, resolution of 10 g, with a range from 0 to 120 kg. Tare has been previously performed.

❑ For internal hive temperature: accuracy of 0.5°C, resolution of 0.1°C, with a range from -10°C to 85°C. Cable length should be 1.5 m.

❑ For battery status: expressed in percentage, with accuracy of 1% and resolution of 1%.

❑ For humidity sensors inside the hive: accuracy of 2%, resolution of 0.1%, with a range from 0 to 100%.

Medium Level of Requirement:

❖ For external hive temperature: accuracy of 0.5°C and resolution of 0.1°C.

❖ For humidity outside the hive: accuracy of 2% and resolution of 1%.

❖ Multiple temperature sensors inside the hive (maximum 3).

❖ Measurement of external brightness expressed in lux.

Alerts to be generated when:

Swarming, Hive theft, Hive weight too low, Hive weight too high,Temperature too low, Low battery charge.

We used an Arduino code per sensor. The sensor values ​​had to be sent to a **connected cloud network.**

# The Things Network

The Things Network (TTN) is a global decentralized network dedicated to the Internet of Things (IoT), utilizing LoRaWAN (Long Range Wide Area Network) technology. This network was created with the aim of providing an **open and free infrastructure for connecting IoT devices over long distances with minimal energy consumption** . All of these characteristics are ideal and align with our project.

For the configuration of The Things Network, we did : 
• The Creation of a DEVICE: AppKey, DevEUI, registration of our microcontroller MKRWAN 1310
➢ The Configuration of the webhook
• A webhook is a means by which a web application informs another web application in real time when a specific event occurs

### For data transmission, we required to work on the payload formatter

The payload formatter takes the actual data that needs to be transmitted and structures it in a way that conforms to the requirements of the communication protocol being used. This ensures that the data can be correctly interpreted and processed by the receiving system or device.

For data processing: it was necessary to know the type of data sent, then transform the information into readable data.

##image##

So far, we spent time testing the sensors and sending their values to The Things Network. However, we had to send the data to another website so that beekeepers would have an interface with usable time graphs of the measured values

# BEEP 

The free BEEP app is a digital registration system for beekeepers and researchers. It provides a total overview of all apiaries and hives of a beekeeper.
On this app, we had to create a section for each sensor. Through this app, we had to link the Things Network : 








