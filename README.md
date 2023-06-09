# Raspberry Pi Weather Station and Automated Watering System

This is an IoT project combines a weather station, soil moisture sensor, and automated watering system using a Raspberry Pi. The Raspberry Pi communicates with an EC2 server to control the device's state (ON/OFF) and post the latest data. This README provides an overview of the project, setup instructions, and usage guidelines.

## Project Overview

The goal of this project is to create a smart system that monitors weather conditions, measures soil moisture, and automatically waters plants when necessary. The Raspberry Pi serves as the central control unit, gathering data from the weather station and soil moisture sensor, and controlling the automated watering system using a relay.

The Raspberry Pi communicates with an EC2 server, which acts as a centralized hub for managing the device's state and storing the collected data. The server also provides a user interface for monitoring the weather conditions, soil moisture levels, and controlling the watering system remotely.

## Hardware Requirements

To set up this project, you will need the following hardware components:

- [Raspberry Pi (preferably Raspberry Pi 3 or newer)](https://www.raspberrypi.com/products/raspberry-pi-3-model-b/)
- Weather station sensor (e.g., DHT11, DHT22, or BME280, we used a [DHT22 Compatible with AM2302 Temperature and Humidity Sensor Module](https://www.amazon.co.uk/AZDelivery-DHT22-modul-parent/dp/B07Z6JRMCW))
- [Capacitive Soil Moisture Sensor](https://www.amazon.com/Gikfun-Capacitive-Corrosion-Resistant-Detection/dp/B07H3P1NRM)
- Relay Module, any relay module should work, I used [this one](https://www.amazon.com/SunFounder-Channel-Shield-Arduino-Raspberry/dp/B00E0NSORY/ref=asc_df_B00E0NSORY/?tag=hyprod-20&linkCode=df0&hvadid=309820150211&hvpos=&hvnetw=g&hvrand=7989239664231727002&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9033313&hvtargid=pla-438786682067&psc=1), but for simplicity, a [relay-controlled power outlet](https://www.adafruit.com/product/2935?gclid=CjwKCAjw4ZWkBhA4EiwAVJXwqQGNsW1u9QZrBkHLJOQRrofrqzBKsTh-y0vbhe1jpZffl53WyPut5hoCDd4QAvD_BwE) would require less modification to the water pump
- Watering system (e.g., water pump, solenoid valve, or sprinkler system)
- Jumper wires and breadboard (for circuit connections)
- Power supply for Raspberry Pi and other components
- Water Pump (I used [this one](https://www.amazon.com/gp/product/B07MDBYTLS/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1))
- Internet connectivity (Ethernet or Wi-Fi)

### Schematics - how to connect the pieces...

Note that this is just a general overview of how each pieces are connected, for detailed instructure, please refer to the documentation of each hardware and the raspberry pi GPIO pinout chart. Also it's advised to use common safety practice when working with electricity, integrated circuits, and AC currents. 

![Schematics for the pi](https://github.com/clueless-caterpillars/plant-water-raspberry-code/blob/main/schematics.png)

## Software Requirements

The software requirements for this project are as follows:

- Raspberry Pi OS (Raspbian) or a compatible operating system
- Python 3.x
- Node 12.x
- AWS SDK for Node
- Web server (see [this repo](https://github.com/clueless-caterpillars/state-server))

## Installation

Set up the Raspberry Pi by installing the Raspberry Pi OS and configuring it according to the manufacturer's instructions.

Connect the weather station sensor, soil moisture sensor, and relay module to the Raspberry Pi using jumper wires and a breadboard. Refer to the documentation or pinout diagrams for your specific sensors and modules.

Install the required software packages on the Raspberry Pi. Open a terminal and execute the following commands:

1. Copy code to your raspberry pi:

$ git clone https://github.com/yourusername/your-repo.git

To install the node dependencies: 

$ npm install

To set-up the Python dependecies:

$ sudo apt update

$ sudo apt install python3-gpiozero

2. Set up the EC2 server with the necessary software stack, including a web server, web application framework, and database management system. Refer to the documentation of the specific components you choose for detailed installation instructions.

## Usage
To start the project, follow these steps:

1. Connect all the hardware components to the Raspberry Pi, ensuring proper wiring and connections.
2. Power on the Raspberry Pi.
3. On the Raspberry Pi, navigate to the project directory and run the main script on `index.js`


