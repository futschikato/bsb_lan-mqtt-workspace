
**mqtt**

Um die vom BSB-lan gesendeten mqtt-Nachrichten zu nutzen benötigt es zunächst einen einen Broker wie z.B. Mosquitto.
Um weiter die Daten mit Grafana visualisieren zu können, benötigen wir noch eine Datenbank. Für so IOT-Sachen ist wohl InfluxDB am besten.
Schema sieht nun so aus :
![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/mqtt_main.png)

Um die Daten vom Broker einzusammeln und in die DB zu schreiben nutzen wir Telegraf .

Installationen:

 - Mosquitto
 - InfluxDB
 - Telegram für InfuxDB
 - Grafana


Grafana:

![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/grafana01.png)

Einstellungen:
![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/grafana02.png)

Um eventuell schnell zu Ergebnissen zu kommen wäre auch Node-Red eine Möglichkeit. Alledings sind die hier Dashboards nach einem Neustart weg.
Unter [TheThingbox](http://thethingbox.io/) kann man sich eine fertiges Raspi-Image herunterladen und hat darauf bereits einen Mosquitto-Broker und Node-Red bereits installiert.

![](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/nodered01.png)

![enter image description here](https://raw.githubusercontent.com/futschikato/mqtt-bsb_lan-workspcae/master/pic/nodered02.png)
