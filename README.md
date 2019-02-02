
**Der BSB lan mit mqtt - ein Überblick**

Um die vom [BSB-lan](https://github.com/fredlcore/bsb_lan) gesendeten mqtt-Nachrichten zu nutzen benötigt es zunächst einen Broker wie z.B. [Mosquitto](https://mosquitto.org/).
Damit wir die Daten mit [Grafana](https://grafana.com/) visualisieren können, benötigen wir ebenfalls eine Datenbank. Für so IOT-Sachen ist wohl [InfluxDB](https://www.influxdata.com/time-series-platform/influxdb/) am besten.
Schema sieht nun so aus :

![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/mqtt_main.png)

Um die Daten vom Broker einzusammeln und in die DB zu schreiben nutzen wir Telegraf.

Installationen Zusammenfassung:

 - Mosquitto
 - ![InfluxDB](https://github.com/futschikato/bsb_lan-mqtt-workspace/blob/master/01-influxdb.md)
 - ![Telegraf für InfluxDB](https://github.com/futschikato/bsb_lan-mqtt-workspace/blob/master/02-telegraf.md)
 - ![Grafana](https://github.com/futschikato/bsb_lan-mqtt-workspace/blob/master/03-grafana.md)


Grafana:

![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/grafana01.png)

Einstellungen:

![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/grafana02.png)

Um eventuell schnell zu Ergebnissen zu kommen wäre auch Node-Red eine Möglichkeit. Alledings sind die hier Dashboards nach einem Neustart weg.
Unter [TheThingbox](http://thethingbox.io/) kann man sich eine fertiges Raspi-Image herunterladen und hat darauf bereits einen  Mosquitto-Broker und Node-Red installiert.

![](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/nodered01.png)

![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/nodered02.png)




