# IIH Essentials application example

This example shows how to use the Industrial Edge App "IIH Essentials" for data modelling and stooring data.

- [IIH Essentials application example](#iih-essentials-application-example)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisities](#prerequisities)
    - [Used components](#used-components)
    - [TIA Project](#tia-project)
  - [Configuration steps](#configuration-steps)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [License and Legal Information](#license-and-legal-information)


## Description

### Overview

This document describes the process of retrieving data from a PLC and integrating it into IIH Essentials application. It also covers data modelling and storage as time-series data for further usage.
IIH Essentials is the foundation for leveraging additional Industrial Edge Apps such as Performance Insight or Notifier.

![overview](docs/graphics/overview.png)

### General task

This examples retrieves data from a PLC through the OPC UA Connector, publishing it on the Databus for IIH Essentials to gather essential shop floor data.   
After connecting IIH Essentials to Databus the incomming data is modeled using Assets and Aspect. An Asset model allows you to create a digital representation of your machine or automation system.   
The data is collected, stored in a database for a specific time period and made accessible via a REST-API for further processing. 

## Requirements

###  Prerequisities

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industial Edge Device on IEM
- Installed Configurators for Databus and OPC UA Connector
- Installed Apps on IED:
  -  Databus
  -  OPC UA Connector
  -  IIH Essentials
- Edge device is connected to PLC
- TIA portal project loaded on PLC
- HTML5-capable Internet browser

### Used components

- Industrial Edge Management (IEM) V1.16.11
  - Databus V2.3.2-5
  - Databus Configurator V2.3.2-2
  - OPC UA Connector V2.x.x
  - Common Connector Configurator V1.9.1-1
  - IIH Essentials V1.10.x
- Industrial Edge Device V1.12.0-3-a
- TIA Portal V16
- S7-PLCSIM Advanced V3.0

### TIA Project

The used TIA Portal project can be found in the miscellaneous repository under "[tank application](https://github.com/industrial-edge/miscellaneous/tree/main/tank%20application)".

## Configuration steps

You can find the further information about the following steps in the [docs](docs/Installation.md)
- Configure PLC Connection (Databus, OPC UA Connector)
- Configure IIH Essentials

## Usage

Once the IIH Essentials app is configured and data is available from a running PLC, process data is collected.
Now the data can be retrieved via REST-API by apps like Performance Insight or Notifier.

## Documentation

You can find further documentation and help in the following links

- [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
- [Industrial Edge Forum](https://forum.industrial-edge.siemens.cloud)
- [Industrial Edge Documentation](https://docs.industrial-edge.siemens.cloud/)
- [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
- [Industrial Edge GitHub page](https://github.com/industrial-edge)
   
## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform.
Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.

## License and Legal Information

Please read the [Legal information](LICENSE.md).
