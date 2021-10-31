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

##### Example Connections

* B -> O
* P <--> C (<--> C + P <--> P)
 * Similar to the Client Server Model:
  * (C = Client) <--> (P = Server) <-- (Sensors)

##### Bluetooth Architecture:

This is a general representation of Bluetooth architecture:
1. Controller
2. Host
3. Profiles

How it looks (From the top down):
* Profiles (Application Layer)
  * Alert Notification, Blood Pressure, Glucose, Heart Rate, HID over GATT, Proximity, ETC...
  * Profiles
    * Describes how two devices can discover each other and how they can communicate
    * Each profile can have multiple services
    * Describes the overall functionality of the device
  * Service
    * A collection of device characteristics and behaviors
    * Might contain more than one characteristic
      * 1. Services defined by SIG (Hear rate service)
      * 2. Custom services
  * Characteristics
    * Numeric values and the actual data that a user can access and use for different purposes (i.e. temperature value, battery percentage, etc.
  * UUID (Universally Unique Identifier)
    * Each service or characteristic is an attribute and all the attributes have a Unique ID called UUIS
    * 128 bits long, so it has to transmit 16 bytes for each UUID   
* Host
  * Security Manager Protocol (SMP)
    * Provides pairing and key distribution for securing communication 
  * Generic Access Profile (GAP)
    * Responsible for handinling device access methods and processes including device discovery, connection establishment, connection termination and bonding 
  * Generic Attribute (GATT)
    * A base profile for all top-level LE profiles
    * Defines how a bunch of ATT attributes are grouped together into meaningful services 
  * Attribute (ATT)
    * Specifies how to access data using a client server model
    * Data is stored in attributes which can be accessed by the client
    * Composed of three basic elements:
      * 1. 16-bit handle
      * 2. UUID which defines the attribute type 
      * 3. Value of a certain length 
  * Logical Link Controller and Adoption Protocol (L2CAP)
    * Provides Data Encapsulation services to the upper layer and allows end to end data communication 
  * Host Controller Interface (HCI)
* Controller
  * Host Controller Interface (HCI)
    * Provides a standardized interface between Host Layer and the Upper Layers which can be interfaced by an application program's API or use a hardware interface like UART, SPI or USB to control by sending commands and data
    * Passes HCI Send data and events to the host,the host passes HCI Send commands and data to the controller
  * Link Layer (LL)
    * Responsible for advertising, scanning, establishing and maintaining connections
    * Also makes sure the data packets are arranged in correct order and are transmitted correctly
    * Has 5 States:
      * Standby, Advertising, Scanning, Initiating, and Connection State  
  * Physical Layer (PHY)
    * 2.4 GHz Frequency band (2.4000 GHz to 2.4835 GHz)
    * Divided into 40 RF Channels
    * 3 Channels (37, 38, 39) are fixed for Broadcasting data whereas the other 37 are used for communication purposes
    * Data transmission rate can be set to 1 Mbps or 2Mbps   

##### How Data is Transferred

1. Notifications:
  * Faster way to transmit data (transmits without acknowledgement signal from client)
3. Indications:
  * Needs an acknowledgement signal after data transfer (Client has to send an acknowledgment signal before a new transfer)

#### More About Advertisements

1. Directed Advertisement:
  * Suitable for known peer devices
2. Undirected Advertisement:
  * General advertiesment and is broadcasted + any scanning device can request for a connection and it can accept
3. Non-connectable Advertisement:
  * Can advertise its data but cannot accept any connections
4. Discoverable Advertisement (Scannable Advertisement):
  * Can respond to scans but it also does not allow connections

##### How Scanning Works

1. Scan Window: Time period for one scan
2. Time Interval: Time interval between each scan

##### Pairing and Bonding

1. Pairing: Authenticating of another device by `Establishes COnnection using` shared keys which can be used to encrypt links
  * Just Works
  * Passkey Entry
  * Numeric Comparison
  * OOB (Out of Band) (NFC)
3. Bonding: Bonding is pairing followed by distributio of keys which can encrypt the links in future reconnections.

[Software Demo Video](http://youtube.link.goes.here) # TODO

## Network Communication

The architecture used is BLE.

The following program is not of my own creation. I am using this beginner code as a means to understand bluetooth low energy development and explain my understanding of BLE.

This program allows for a bluetooth nrf52840 Dongle to connect to the nrf52840 Developer Kit which acts as the Peripheral.

The Dongle acts as the central in which we can observe and respond to the peripheral.

In the case of this simple project

{Identify the format of messages being sent} # TODO

## Development Environment

##### Tools
* nrf52840 Dongle
* nrf52840 DK
* Segger Embedded Studio for ARM V5.64 - Non-Commercial License
* NRF Connect v3.7.2

##### Languages
* C

## Useful Websites

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

* Learn to program advertisement
* Learn to create, design, and code BLE Profiles
* Continue Learning Bluetooth Technology
* Segue into Ultra Wideband Programming
