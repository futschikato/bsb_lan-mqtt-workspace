1.  InfluxDB, als Datenbank
2.  Telegraf als Collector (inkl. mqtt_input-Plugin)
3.  Grafana als Visualisierung

**2. Telegraf mit mqtt_input Plugin**

[Installation Telegraf](https://docs.influxdata.com/telegraf/v1.9/introduction/installation/)



Konfiguration mit dem mqtt_consumer Input erzeugen:


[cubase:~#] telegraf -sample-config -input-filter mqtt_consumer -output-filter influxdb > telegraf.conf

Konfiguration bearbeiten:

[cubase:~#] vi /etc/telegraf/telegraf.conf



```
**#              OUTPUT PLUGINS                  #**

database = "telegraf" # required 

**#         SERVICE INPUT PLUGINS             #**

[[inputs.mqtt_consumer]]
  servers = ["mosquitto:1883"]
  qos = 0
  topics = [ "#" ]
  data_format = "value"
  data_type = "float"
```


Erklärung:

``` topics = [ "#" ]  ```

liest zB. alle topics des Brokers

``` topics = [
    "UVR2MQTT/#",
    "BSB-LAN/#",
    "/raspi/#",
    "/esp/#",
    "uvr1611/#",
  ]   ```
  
  auch Auflistung mehrerer topics möglich.
  Aber keine Mischung der data_type, also entweder alles float oder


Telegraf nach influx starten:

[cubase:~#] vi /lib/systemd/system/telegraf.service



After=network.target influxdb.service




Test ob Daten in InfluxDB geschrieben werden:


[cubase:~$] influx
```
>use telegraf
>show measurements
>select * from mqtt_consumer
>exit
```


https://github.com/influxdata/telegraf/tree/master/plugins/inputs/mqtt_consumer

