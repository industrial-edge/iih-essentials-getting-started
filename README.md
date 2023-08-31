# Data Service application example

This example shows how to use the Industrial Edge App "Data Service" to model data structure and store data.

- [Data Service application example](#data-service-application-example)
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
  - [Disclaimer](#disclaimer)


## Description

### Overview

This document describes how to get the data from a PLC into the app Data Service, prepare the data and store timeseries for further usage.
A properly configured Data Service is the basis for using other Industrial Edge Apps (e.g. Performance Insight or Notifier).

![overview](docs/graphics/Overview.PNG)

### General task

The example reads data from a PLC via the OPC UA Connector.
The data is published on the Databus, where the Data Service can collect the needed shopfloor data.
First an adapter for providing the datapoints must be assigned and configured.
Afterwards the data structure can be modeled using assets and aspects.
Assets are used to structure the plant in logical units.
Within an asset you can create variables and link them to the appropriate datapoints, which are made available by the configured adapter.
This data is collected, saved for individual time period and transfered for further processing.
By creating an aspect, variables can be grouped to a logical unit.

## Requirements

###  Prerequisities

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industial Edge Device on IEM
- Installed System Configurators for Databus and OPC UA Connector
- Installed System Apps Databus and OPC UA Connector
- Installed Data Service
- Edge device is connected to PLC
- TIA portal project loaded on PLC
- HTML5-capable Internet browser

### Used components

- Industrial Edge Management (IEM) V1.5.2-4 / V1.11.8
  - Databus V2.0.0-4
  - Databus Configurator V2.0.0-5
  - OPC UA Connector V1.8.1
  - Common Connector Configurator V1.8.1-4
  - Data Service V1.6.0
- Industrial Edge Device V1.10.0-9
- TIA Portal V16
- S7-PLCSIM Advanced V3.0

### TIA Project

The used TIA Portal project can be found in the miscellaneous repository under "[tank application](https://github.com/industrial-edge/miscellaneous/tree/main/tank%20application)".

## Configuration steps

You can find the further information about the following steps in the [docs](docs/Installation.md)
- Configure PLC Connection (Databus, OPC UA Connector)
- Configure Data Service

## Usage

Once the Data Service app is configured and data is availalbe from a running PLC, process data can be collected.
Now the data can be used to feed other apps like Performance Insight or Notifier.

## Documentation

- You can find further documentation and help in the following links
  - [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
  - [Industrial Edge Forum](https://forum.mendix.com/link/space/industrial-edge)
  - [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
  - [Industrial Edge GitHub page](https://github.com/industrial-edge)
  - [Industrial Edge documentation page](https://docs.eu1.edge.siemens.cloud/index.html)

## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform. Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.

## License and Legal Information

Please read the [Legal information](LICENSE.txt).

## Disclaimer

IMPORTANT - PLEASE READ CAREFULLY:

This documentation describes how you can download and set up containers which consist of or contain third-party software. By following this documentation you agree that using such third-party software is done at your own discretion and risk. No advice or information, whether oral or written, obtained by you from us or from this documentation shall create any warranty for the third-party software. Additionally, by following these descriptions or using the contents of this documentation, you agree that you are responsible for complying with all third party licenses applicable to such third-party software. All product names, logos, and brands are property of their respective owners. All third-party company, product and service names used in this documentation are for identification purposes only. Use of these names, logos, and brands does not imply endorsement.
