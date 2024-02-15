# Configuration

- [Configuration](#configuration)
  - [Configure PLC Connection](#configure-plc-connection)
    - [Configure Databus](#configure-databus)
    - [Configure OPC UA Connector](#configure-opc-ua-connector)
  - [Configure IIH Essentials](#configure-iih-essentials)
    - [Configure the adapter](#configure-the-adapter)
    - [Configure an Asset with variables](#configure-an-asset-with-variables)
    - [Configure an Aspect](#configure-an-aspect)

## Configure PLC Connection

To retrieves data from a PLC with OPC UA Server and provide it for Edge Applications we will use the OPC UA Connector. The OPC UA Connector establishes a connection to the PLC via the OPC UA protocol and publishes data to Databus, where IIH Essentials gathers the required data. 
In order to setup IIH Essentials, first these apps must be configured properly:

- Databus
- OPC UA Connector

### Configure Databus

1. In your `IEM` go to `Data Connections` and launch the `Databus configurator`.
2. Create a user and grant permission to access topic. For example:
   - Username: `edge`
   - Password: `edge`
   - Topic name: `ie/#`
   - Permission: `Publish and Subscribe`

<p><kbd><img src="graphics/IE_Databus_User.PNG"/></kbd></p>

<p><kbd><img src="graphics/IE_Databus.PNG"/></kbd></p>

3. Deploy the configuration.

### Configure OPC UA Connector

1. In your `IEM` go to `Data Connections` and launch the `OPC UA Connector configurator`.
2. Add a data source:

<p><kbd><img src="graphics/S7_Connector_Data_Source.PNG"/></kbd></p>

3. Add tags:

<p><kbd><img src="graphics/opcuaconnector.png"/></kbd></p>

   - ProducedBottles: ns=3;s="GDB"."process"."numberProduced"
   - FaultyBottles: ns=3;s="GDB"."process"."numberFaulty"
   - TankLevel: ns=3;s="GDB"."signals"."tankSignals"."actLevel"	
   - TankTemperature: ns=3;s="GDB"."signals"."tankSignals"."actTemperature"	

4. Configure settings:

<p><kbd><img src="graphics/opcuaconnector_settings.png"/></kbd></p>

Hint: Enter username and password of user created in Databus Configurator.

5. Deploy project.

## Configure IIH Essentials

In your IED Web UI open the app IIH Essentials.

### Configure the adapter

1. Click on the icon `Settings` on the left sidebar. Then open `Databus Settings` and enter username and password of user created in Databus Configurator.

<p><kbd><img src="graphics/iihessentials_databus_settings.png"/></kbd></p>

2. Click on the icon `Connectors` on the left sidebar. To add a connector click on the `plus` icon. IIH Essentials discovers automatically all available connectors. In this case OPC UA Connector is shown. 

<p><kbd><img src="graphics/iihessentials_addconnector.png"/></kbd></p>

3. To use the connector click on `Add`. After that the connector must be activated. Therfore select this connector and click on `edit`, set status to activated and save

<p><kbd><img src="graphics/iihessentials_opcuaconnector.png"/></kbd></p>

The connector (here OPC UA Connector) is now activated and connected to the IIH Essentials.

<p><kbd><img src="graphics/iihessentials_opcuaconnector_status.png"/></kbd></p>

### Configure an Asset with variables

An Asset is a digital representation of a machine or automation system with one or more automation units (e.g. PLC). The data that describes an Asset is collected and transferred. The data is then made available for further processing and evaluation.

1. On the left sidebar click the icon `Assets & Connectivity`. For the "edge" Asset you can add child Assets as needed. Click `Create first variable` or `Add variable` on the right side to add one or more tags. 
2. Choose OPC UA Connector and select one or multiple tags.

<p><kbd><img src="graphics/iihessentials_addvariable.png"/></kbd></p>

After adding all variables it looks as following

<p><kbd><img src="graphics/Data_Service_Assets.PNG"/></kbd></p>

Using the **variables preview**, you can immediately check whether data is transmitted from the Databus:

<p><kbd><img src="graphics/Data_Service_Preview.PNG"/></kbd></p>

The **data storage period** can be set individually for each Asset. The data is deleted from the disk after this time.
To change the this time period, click on the edit next to the name of the Asset:

<p><kbd><img src="graphics/Data_Service_Retention.PNG"/></kbd></p>

### Configure an Aspect

An Aspect is a mechanism for data modeling of Assets. Aspects group related data points (topics) based on their logical assignment.

Choose the register "Aspects" to create a new Aspect by clicking "Create first Aspect" or "Add Aspect".

<p><kbd><img src="graphics/iihessentials_addaspect.png"/></kbd></p>

Hint: An Aspect can include several variables, but each variable can only be assigned to one Aspect.

<p><kbd><img src="graphics/iihessentials_aspects.png"/></kbd></p>

