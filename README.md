# Bluetooth-Low-Energy

# Overview

As a software engineer I want to further my learning by learning Bluetooth. Specifically I will be focusing on Bluetooth Low Energy.

For this repository I will be attempting to experiment around with bluetooth and keep this repository as a place for anyone to refer to who is getting started in Bluetooth Development.

After trudging through numerous sources finding tutorials and correct sources to get started in bluetooth may be a bit confusing. I hope that through this README I can provide my personal journey of sorts and links to websites or sources that will be essential or useful to anyone starting.

## Personal Notes (To be organized later):
  * Reference: Sumair's Embedded Engineering Series

### Bluetooth - Introduction

##### History:

* Bluetooth was initially developed by Dr. Jaap Haartsen at Ericsson in 1994.
* Mobile Market was growing faster and faster so a standard wireless communication was needed.
  * Ericsson, Nokia, IBM, Intel and TOshiba created a group named SIG (Special Interest Group) to create a standard for communication among mobile devices.
* (FUN FACT: The bluetooth symbol is a Nordic Initial for "H.B." after the famous Nordic Viking Harald "Bluetooth" who united countries in the Norwegain area during his time.)

##### BLE & Features

* BLE stands for Bluetooth Low Energy
  * BLE features an ultra low power protocol which uses less time on air and allows the devices to sleep for longer time periods while the connection is not being used
  * BLE devices can consume very less power and can even work for more than a year on just a single coin bettery
  * Highly Secure with AES-128 encryption
  * Long transmission Distrance can be achieved
  * Instant connection with devices

##### Applications of Bluetooth

* Medical
* Fitness & Support
* Computers and Games
* Advertisement
* IOT
* ETC.

##### Roles in BLE

1. __Broadcaster (B)__ (Not as used)
  * Advertises data only and cannot connect with other devices
2. __Observer (O)__ (Not as used)
  * Scans for advertised data and can receive advertised data but cannot connect to other devices
3. __Central (C)__ (Mostly Used)
  * A master device in Bluetooth which scans for advertisement packets
  * Initiates connection and is capable of connecting with other Peripherals (Slave devices) upon receiving advertisement packets 
  * Can connect with multiple Peripherals (slave) devices
  * Examples: Mobile Phones
5. __Peripheral (P)__ (Mostly Used)
  * A slave device which advertises its data and connect with Masters
  * Examples: Sensors
* (A single device can support multiple roles - nrf52840 devices and similar)



[Software Demo Video](http://youtube.link.goes.here) # TODO

## Network Communication

{Describe the architecture used} #TODO

{Identify the format of messages being sent} # TODO

## Development Environment

{Describe the tools that you used to develop the software}

{Describe the programming language that you used and any libraries.}

## Useful Websites

{Make a list of websites that you found helpful in this project}
* [4 Essential Tools for Every Bluetooth Low Energy Developer](https://www.bluetooth.com/blog/4-essential-tools-for-every-bluetooth-low-energy-developer/)
* [Sumair's Embedded Engineering (Start at Part 40 - Extremely Helpful)](https://www.youtube.com/watch?v=AQu80Fdn3T8&list=PLiKJljyEUlZj4z8RqJKTaoMpSqjLdBGO4&index=43)
* [An Introduction to Bluetooth Low Energy Development](https://www.bluetooth.com/bluetooth-resources/bluetooth-le-developer-starter-kit/)
* [Bluetooth low energy Characteristics, a beginner's tutorial (2016)](https://devzone.nordicsemi.com/nordic/short-range-guides/b/bluetooth-low-energy/posts/ble-characteristics-a-beginners-tutorial)
* [Nordic YouTube Channel](https://www.youtube.com/user/NordicSemi/featured)

## Essential Tools
* [nrf52840 Dongle (You will need this)](https://www.nordicsemi.com/Products/Development-hardware/nRF52840-Dongle)
* [nrf52840 Developer Kit (If you get this, even better)](https://www.nordicsemi.com/Products/Development-hardware/nRF52840-DK)
* [Getting Started with nrf52840 Developer Kit](https://www.nordicsemi.com/Products/Development-hardware/nRF52840-DK/GetStarted#infotabs)
* [nrf Tools Documentation](https://infocenter.nordicsemi.com/index.jsp?topic=%2Fug_nrf52840_dk%2FUG%2Fdk%2Fintro.html)

# Future Work

{Things to fix, improve, and add in the future.}
* TODO
* TODO
* TODO
