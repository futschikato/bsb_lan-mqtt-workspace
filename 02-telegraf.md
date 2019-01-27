1.  InfluxDB, als Datenbank
2.  Telegraf als Collector (inkl. mqtt_input-Plugin)
3.  Grafana als Visualisierung


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
  topics = [ "mydevice/#" ]
  data_format = "value"
  data_type = "float"
```




Telegraf nach influx starten:

[cubase:~#] vi /lib/systemd/system/telegraf.service


```
After=network.target influxdb.service
```



Test ob Daten in InfluxDB geschrieben werden:


[cubase:~$] influx
```
>use telegraf
>show measurements
>select * from mqtt_consumer
>exit
```



https://github.com/influxdata/telegraf/tree/master/plugins/inputs/mqtt_consumer[Link](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/mqtt_consumer)