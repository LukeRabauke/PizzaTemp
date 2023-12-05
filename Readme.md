--> PIZZATemp <--

Within this repo I am providing everything you will need to build your own high temperature (±450°C) thermometer for your smart home (bases on Home Assistant and ESPHome). 







Short (and unsorted) Documentation

List of components:
- Batteryshield for Wemos D1 Mini v1.1.0 (from Ali)
- 100k Ohm Resistor 
- Wemos D1 Mini (from Ali)
- OLED Display 1.3" (from Ali)
- 3D Print Housing (link to be added)
- Amplifier (Link to be added)
- Temperature Sensor (Link to be added)

----------------------------------------------------------------------------------
Battery Voltage:
![Alt text](image-1.png)
Battery SoC:
![Alt text](image.png)
----------------------------------------------------------------------------------
Berechnung Faktor für Analogwandlung inkl Spannungsteiler:

Spannungswert mit Faktor 1: 0,07 V
Real gemessene Spannung: 0,272 V

Faktor = 0,272/0,07 = 3,886

Korrektur 1:

Spannungswert mit Faktor 3,886: 3.76V
Real gemessene SPannung= 4,06V

Faktor neu = Faktor * (4,06/3,886)= 4.19614
----------------------------------------------------------------------------------
How tos:
- How to ESPHome
Update cli:
    pip3 install -U esphome
Build bin:
    esphome compile YOURYAML.yaml
Flashing via CLI:
    esphome upload --device /dev/cu.usbserial-0257B058 pizzatemp.yaml
----------------------------------------------------------------------------------
Berechnung SoC:
4.2V = 100%
2.75V = 0%

Prozentskala=(Wert−Untere Grenze) / (Obere Grenze−Untere Grenze)×100

(x-2.75)/(4.2-2.75)*100
----------------------------------------------------------------------------------


Source Reference:

Batteryshield Infos:
https://iotspace.dev/wemos-d1-mini-battery-shield/
Spannungsteiler Info:
https://www.nikolaus-lueneburg.de/2016/12/spannungsteiler/
Analogwerte mit ESPHome einlesen:
https://esphome.io/components/sensor/adc.html
Info LiPo Akku:
https://www.lithium-polymer-akkus.de/wiederaufladbarer-lipo-akku-lp053450-3-7-v-900-mah-3-33wh/
Entladungsabschaltung: 2,75 V
Max. Ladespannung: 4,2 V ± 50 mV