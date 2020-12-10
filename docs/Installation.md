# Configuration

- [Configuration](#configuration)
  - [Configure PLC Connection](#configure-plc-connection)
    - [Configure Databus](#configure-databus)
    - [Configure S7 Connector](#configure-s7-connector)
  - [Configure Data Service](#configure-data-service)
    - [Configure the adapter](#configure-the-adapter)
    - [Configure an asset with variables](#configure-an-asset)
    - [Configure an aspect](#configure-an-aspect)
	
	
## Configure PLC Connection

To read data from the PLC and provide the data, we will use S7 Connector to establish connection with the PLC via OPC UA.
The S7 Connector sends the data to the Databus, where the Data Service app can collect what is needed.
In order to build this infrastructure, these apps must be configured properly:

- Databus
- S7 Connector

### Configure Databus

In your IEM open the Databus and launch the configurator.

Add a user with this topic:
`"ie/#"`

![ie_databus_user](docs/graphics/IE_Databus_User.PNG)

![ie_databus](docs/graphics/IE_Databus.PNG)

Deploy the configuration.

### Configure S7 Connector

In your IEM open the S7 Connector and launch the configurator.

Add a data source:

![S7 Connector Data Source](docs/graphics/S7_Connector_Data_Source.PNG)

Add needed tags:

![s7_connector_config](docs/graphics/S7_Connector_Configuration.PNG)

Edit the settings:

![s7_connector_settings](docs/graphics/S7_Connector_Settings.PNG)

Hint: Username and password should be the same for all system apps, e.g. "edge" / "edge".

Deploy and start the project.

## Configure Data Service

In your IED Web UI open the app Data Service.

Hint: If an error screen appears saying "...unauthorized...", please restart the Data Service app, wait a moment and try again to open it.

### Configure the adapter

On the left bar click the icon "Adapters" and choose the SIMATIC S7 Connector (MQTT).

Click the edit icon on the right to open the adapter configuration.

![data_service_adapter](docs/graphics/Data_Service_Adapter.PNG)

Add the missing entries for username and password (again "edge"/"edge") and save it.

![data_service_adapter_config](docs/graphics/Data_Service_Adapter_Config.PNG)

Hint: Sometimes the Data Service app must be restarted, to take over the adapter changes.

### Configure an asset with variables

On the left bar click the icon "Assets & Connectivity". For the "edge" asset you can add child assets as needed.

Choose "Create first variable" or "Add variable" on the right side to add tags.

![data_service_assets](docs/graphics/Data_Service_Assets.PNG)

![data_service_variable](docs/graphics/Data_Service_Variable.PNG)

To change the storage time period, klick on the link below the asset:

![data_service_retention](docs/graphics/Data_Service_Retention.PNG)

### Configure an aspect

Choose the register "Aspects" to create a new aspect by clicking "Create first aspect" or "Add aspect".

![data_service_aspect](docs/graphics/Data_Service_Aspect.PNG)

Hint: An aspect can include several variables, but each variable can only be assigned to one aspect.

![data_service_aspects](docs/graphics/Data_Service_Aspects.PNG)

