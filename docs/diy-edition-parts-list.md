# Parts List: DIY Edition

Shopping list for the DIY Edition — everything you need for the
[DIY Getting Started Guide](../README.md#-diy-getting-started-guide-diy-edition).

No affiliate links here on purpose — just real, checked links to where
you can actually buy the parts, in Germany and the US.

## Core parts

| Part | Qty | Notes |
|---|---|---|
| ESP8266 board, "ESP-12F" / "D1 Mini" | 1 | Any board with the exact PlatformIO id `d1_mini` works with the provided ESPHome config as-is. A different ESP8266 board just needs a one-line change (`board:` in `esphome/hamster-wheel-sensor.yaml`). |
| TCRT5000 infrared reflective sensor module | 1 | The common 3-4 pin breakout board (VCC / GND / D0 or "OUT", sometimes also A0) |
| Jumper wires (female-female, ~10 cm) | 1 set | Any standard set works |
| Micro-USB or USB-C cable (depending on the board) | 1 | For flashing and permanent power |

## Where to buy — Germany

| Retailer | D1 Mini | TCRT5000 | Note |
|---|---|---|---|
| **BerryBase** | [Link](https://www.berrybase.de/en/d1-mini-esp8266-entwicklungsboard) | [Link](https://www.berrybase.de/en/tcrt5000-infrared-sensor-light-barrier) (~€0.30) | One-stop shop for both parts, German maker/Raspberry-Pi specialist |
| **Reichelt** | [Link](https://www.reichelt.de/d1-mini-kompatibles-esp8266-board-v2-0-d1-mini-p253978.html) (~€5.30) | not found in their catalog | Long-established, widely trusted in the hobbyist community |
| **Amazon.de** | [HiLetgo, pack of 5](https://www.amazon.de/HiLetgo-ESP8266-ESP-12F-WiFi-Modul-Stiftleisten/dp/B073CQVFLK) | [Oiyagai, pack of 5](https://www.amazon.de/TCRT5000-Infrarot-Reflektierende-Barriere-Fotoelektrischer-Schalter/dp/B0784L5YTY) | Convenient if you already order from Amazon; marketplace listings rotate — if a link is dead, just search the part name |

## Where to buy — USA

| Retailer | D1 Mini | TCRT5000 |
|---|---|---|
| **Amazon.com** | [CANADUINO WEMOS D1 Mini](https://www.amazon.com/CANADUINO-WEMOS-ESP8266-Wi-Fi-Module/dp/B07B2JVPKX) | [HiLetgo, pack of 10](https://www.amazon.com/HiLetgo-Channel-Tracing-Sensor-Detection/dp/B00LZV1V10) |

Marketplace listings come and go — if either link is dead, both parts
are common enough that searching "D1 Mini ESP8266" / "TCRT5000 IR
sensor module" on Amazon (or Adafruit/SparkFun-adjacent stores) will
turn up plenty of equivalents.

## Cheapest option (slower shipping)

**AliExpress** and **Banggood** are where a lot of hobbyists buy bare
ESP-12F modules and TCRT5000 boards for the lowest price. Trade-off:
shipping from China can take weeks, and quality/QC varies more than
with the retailers above. Fine if you're not in a hurry; search
"D1 Mini ESP8266" / "TCRT5000" directly on either site.

## Last checked

2026-08-07. Prices are ballpark and will drift — check the current
price on the linked page.
