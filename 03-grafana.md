1.  InfluxDB, als Datenbank
2.  Telegraf als Collector (inkl. mqtt_input-Plugin)
3.  Grafana als Visualisierung 

**3. Grafana**

Installation siehe : [Installation Grafana](https://grafana.com/grafana/download?platform=linux)


Damit der Zugriff auf Grafana später einfacher geht, deaktivieren wir die Benutzerregistrierung und aktivieren den anonymen Zugriff auf die Daten:

[cubase:~#] vi /etc/grafana/grafana.ini

```
#################################### Users ###############################
[users]
**# disable user signup / registration**
;allow_sign_up = false


#################################### Anonymous Auth ##########################
[auth.anonymous]
# enable anonymous access
;enabled = true
```
