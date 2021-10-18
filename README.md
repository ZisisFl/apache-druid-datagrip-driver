# Connect DataGrip to Apache Druid 

## Creating the custom Driver
- Navigate to File > New > Driver,  to open Data Sources and Drivers window
- In the new window change **Name** field of the driver to Avatica Apache Druid (or anything else you want to recognize it)
- Go to **Driver Files** hit **+** button and upload all the jar files which can be found in the jars folder of my Github repo
- Select org.apache.calcite.avatica.remote.Driver in the **Class** drop down menu
- Add a **URL template**, name it **default** and set value to:
```sh
jdbc:avatica:remote:url=http://{host::localhost}:{port::8082}/druid/v2/sql/avatica/
```
- Go to tab **Options** and there in the Other section select Generic SQL from the drop down menu
- Apply to save Driver

## Creating a new data source using the custom Driver:
- Navigate to File > New > Data Source > {Druid Driver name}
- Change host and port if needed (default port is set to 8082 because it is the default plaint text port of Broker node)
- Test connection
- Apply to save Data source
