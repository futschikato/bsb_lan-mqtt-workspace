
1.  InfluxDB, als Datenbank
2.  Telegraf als Collector (inkl. mqtt_input-Plugin)
3.  Grafana als Visualisierung

**1. InfluxDB, als Datenbank**

 [Installation Influx](https://docs.influxdata.com/influxdb/v1.7/introduction/installation/)
 
 folgende Änderungen/Anpassung:
 
 sudo vi /etc/influxdb/influxdb.conf  


```
  enabled = true   
  bind-address = ":8086"   
  auth-enabled = false 
```

Nutzer und Datenbank für telegram anlegen:

[cubase:~$] influx

 
```
 Connected to http://localhost:8086 version 1.2.2  
 InfluxDB shell version: 1.2.2  
 >CREATE USER admin WITH PASSWORD '<password>' WITH ALL PRIVILEGES  
 >CREAT DATABASE telegraf  
 >exit
```
