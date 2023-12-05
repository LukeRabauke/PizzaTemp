Komponentenliste:
- Batteryshield für Wemos D1 Mini v1.1.0
- 100k Ohm Widerstand 
- Wemos D1 Mini
- OLED 
- 3D Print Gehäuse
- Messverstärker
- Temperaturfühler

----------------------------------------------------------------------------------
Battery Voltage:

Battery SoC:
![Alt text](image-1.png)


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