# OpenDTU-PCB  [![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)    
   
Eine Leiterplatte für OpenDTU oder Ahoy mit Oled Display.
Gehäuse Gainta G203CMF 115 x 65 x 40

![Top](https://raw.githubusercontent.com/turrican944/OpenDTU-PCB/main/bilder/top%20v2.png)
![Bottom](https://raw.githubusercontent.com/turrican944/OpenDTU-PCB/main/bilder/bottom%20v2.png)
![dtu](https://raw.githubusercontent.com/turrican944/OpenDTU-PCB/main/bilder/dtu.jpg)

Neue PCB Version jetzt mit CMT2300a und NRF24L01+
Es kann ein 1.3" Oled oder 0.9" I2C Oled verbaut werden. Die Polung der Spannungsversorgung ist über Jumper einstellbar. Das Oled kann wahlweise auch 90° gedreht eingesetzt werden. NRF24L01+ als Standart mit PCB Antenne oder auch als Version mit externer Antenne.
Es kann ein Wemos D1 mini oder ein Wemos D1 ESP32 verbaut werden. Für OpenDTU wird der Wemos D1 ESP32 benötigt.

Das GPIO Pinning ist das Standartpinning vom AhoyDTU. OpenDTU muss entsprechend auf angepasst werden (Deviceprofil.json für OpenDTU mit und ohne Display).
GPIO Pins OpenDTU: <br>
NRF: <br>
IO17 IRQ <br>
IO16 CE <br>
IO05 CS <br>
IO23 MOSI <br>
IO19 MISO <br>
IO18 SCK <br>
Display: <br>
IO22 SCL <br>
IO21 SDA <br>
CMT2300a: <br>
IO14 SDIO <br>
IO12 SCLK <br>
IO27 CSN <br>
IO26 FCSB <br>
IO04 GPIO2 <br>
IO13 GPIO3 <br>
LED: <br>
IO32 LED0 <br>
IO33 LED1 <br>

Die Pins legt man am besten schon in der Platformio.ini fest. Der ESP D1 Mini ist in der Platformio.ini schon enthalten allerdings sind dort IO16 und IO17 vertauscht. Flasht man nun den ESP32 wenn der schon auf de Platine ist, gibts beim Starten immer einen Interrupt vom Funkmodul (Pinning stimmt ja nicht) und ggf. kommt man dann nicht auf das WebIF. Also am besten die Pins des Funkmodul schon vorher ändern oder ESP32 erst flashen, devices config nachladen und ESP32 auf der Platine verbauen.

Bauteile: <br>
Wemos D1 ESP32 (für OpenDTU oder Ahoy) https://www.az-delivery.de/collections/esp32/products/esp32-d1-mini <br>
NRF24L01+ Funkmodul <br>
470uF Kondensator (es müssen wohl nicht umbedingt 470uF sein, weniger geht wohl auch ggf das nehmen was in der Bastelkiste grade ist)<br>
Minicombicon wenn die Stromversorgung nicht über den USB Port erfolgen soll. https://www.reichelt.de/stiftleiste-2-pol-rm-3-81-mm-0--ctb932ve-2-p292580.html?&nbc=1&trstct=lsbght_sldr::292630 <br>
Gainta G203CMF 115 x 65 x 40 Gehäuse https://www.conrad.de/de/p/gainta-g203cmf-universal-gehaeuse-115-x-65-x-40-polycarbonat-hellgrau-klar-1-st-2356897.html <br>
Ahoy mit einem ESP32 habe ich auf der aktuelle Platine nicht getestet.

Olimex ESP32 Poe
Adapterplatine CMT2300a auf Olimex poe Board
![Olimex1](https://raw.githubusercontent.com/turrican944/OpenDTU-PCB/main/bilder/olimex1.jpg)
![Olimex1](https://raw.githubusercontent.com/turrican944/OpenDTU-PCB/main/bilder/olimex2.jpg)
![Olimex1](https://raw.githubusercontent.com/turrican944/OpenDTU-PCB/main/bilder/olimex.jpg)
Die Gerberdaten der Olimex Platine sind auch Panel 2x4 vorhanden.

Gehäuse für den Olimex ISO
https://www.thingiverse.com/thing:6489072 <br>
Gehäuse Olimex https://www.thingiverse.com/thing:4860626 (das ist das auf dem Bild)

[![Creative Commons Lizenzvertrag](https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-sa/4.0/)

Dieses Werk ist lizenziert unter einer [Creative Commons Namensnennung - Nicht-kommerziell - Weitergabe unter gleichen Bedingungen 4.0 International Lizenz](http://creativecommons.org/licenses/by-nc-sa/4.0/).
