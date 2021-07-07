# How to sample high frequency signals from PLC to Edge Computing applications via MQTT (Using Node-RED, SIMATIC PLC and OPC-UA)

This document will take you through the basic steps and configuration of components required to set up a PLC program with the SIEMENS library "LEdgeBuffer" to  recording and send high frequency signals' data to an edge computing application using OPC-UA and Node-RED or SIEMENS Industrial flow creator.

The document intends to provide a quick start guide for testing the library locally with any SIMATIC PLC S7-1500 and Node-RED/SIEMENS Industrial Flow Creator.

* [Writing good how-to or tutorial](#writing-good-how-to-or-tutorial)
  * [Description](#description)
    * [Overview](#overview)
    * [General Task](#general-task)
  * [Requirements](#requirements)
    * [Prerequisites](#prerequisites)
    * [Used components](#used-components)
  * [Installation](#installation)
  * [Usage](#usage)
  * [Documentation](#documentation)
  * [Contribution](#contribution)
  * [Licence and Legal Information](#licence-and-legal-information)

## Description

The SIMATIC library "LEdgeBuffer" allows creating a local buffer in the PLC to sample high speed signals (i.e. sampling period = 1ms). This buffer and the recording job can be accessed and controled via OPC-UA.

The PLC library functions (FCs) work together with a Node-RED flow. This flow interacts with the PLC "buffer" to start the recording process and later collect the recorded data. The interaction is done reading/writing a datablock via OPC-UA that works as an interface for the PLC application and user consuming the data from the buffer.

The Node-RED flow works as a gateway to publish the data from the PLC as a JSON file that can be send to another devices via i.e. MQTT.


### Overview

This how-to has been created as a straight forward example to sample PLC signals to the edge in asynchronic way, but keeping timestamps. 

The purpose is to guide PLC users into the steps to connect their signals into the application "LEdgeBuffer" for the use case of reading the signals remotely and processing into the edge.

### General Task

What is the general goal/task of this how-to/tutorial?

![task](docs/graphics/example_graphic.png)

## Requirements

### Prerequisites

User should be familiar with:
* Node-red
* PLC programming
* TIA Portal V16
* MQTT

### Used components

*Industrial Edge Management (IEM) V1.2.14
 *S7 Connector V1.2.26
 *S7 Connector Configurator V1.2.37
 *IE Databus V1.2.16
 *IE Databus Configurator V1.2.29
*Industrial Edge Device (IED) V1.2.0-56
*TIA Portal V16
*PLC: CPU 1511 FW 2.8.3

if the user cannot get a SIEMENS industrial edge system, this example can also be done, using Node-RED

For installing node-red check the next link:
* [Node-RED installation](https://nodered.org/docs/getting-started/local)

## Installation

1. First step the user must import the PLC library into his/her PLC application. see this link 
* Library [SIMATIC: S7-1500 – LEdgeBuffer](https://support.industry.siemens.com/cs/document/109783979)
2. A fork of this github entry must be created 
3. A new project has to be created based on the fork of this library in Node-RED/SIEMENS Industry


## Usage

When the app is installed, how can I use it? Usually some basic UI description to prove that the app is working correctly.

## Documentation

Add links to documentation. Either on external URL or in the doc folder. Please use always link to a file not to a directory (it doesn't work with static site generator engines).

Add these links:

You can find further documentation and help in the following links

* [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
* [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
* [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
* [Industrial Edge GitHub page](https://github.com/industrial-edge)

## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section. Everybody is free to propose any changes to this repository using Pull Requests.

## Licence and Legal Information

Please read the [Legal information](LICENSE.md).
