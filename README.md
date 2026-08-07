# Hamster Fitness — Hardware

[![License](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey.svg)](LICENSE)

> **This is the hardware repository.** It contains the physical wheel
> sensor, 3D-printed enclosure, PCB/wiring notes, and ESPHome firmware for
> [Hamster Fitness](https://github.com/GpsM2/ha-hamster-fitness-integration)
> — a free Home Assistant integration that turns your hamster's running
> wheel into a health score, distance tracking, and more. **The Home
> Assistant integration itself lives in a separate repository:
> [ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration).**

> This repo currently ships the **Bastler-Edition** — a DIY starter
> kit built from cheap, standard parts. It's the fastest way in, and
> the primary target for the ESPHome code here. See
> [ROADMAP.md](ROADMAP.md) for where the project is headed next
> (a plug-and-play PCB edition, then a deluxe E-Ink edition).

## License

This project uses the
[Creative Commons Attribution-NonCommercial 4.0 International license](LICENSE)
(CC BY-NC 4.0): anyone can use, adapt, and share these designs and this
firmware for free, for **non-commercial** purposes (personal use, hobby
projects, schools, research) — with attribution. The author (GpsM2)
keeps full rights and may also use or license the project commercially.
(The software repo uses a different, permissive license — see its
README.)

## What's here

- **`ROADMAP.md`** — product roadmap: Bastler-Edition (DIY, now) →
  Plug-and-Play PCB edition → Deluxe E-Ink edition.
- **`esphome/`** — ESPHome YAML firmware for the wheel-rotation sensor.
- **`cad/`** — OpenSCAD/STL/STEP files for the 3D-printed enclosure
  (nothing here yet).
- **`pcb/`** — schematics/KiCad files, if this ever moves past a
  hand-wired build (nothing here yet).
- **`docs/`** — build guides and bills of materials.

## 🐹 DIY Getting Started Guide (Bastler-Edition)

This is Phase 1 of the [roadmap](ROADMAP.md) and the fastest way to a
working wheel sensor: cheap, off-the-shelf parts, no soldering
required (jumper wires are enough), and no special tools. If you've
ever wired up an Arduino or Raspberry Pi project, this is easier — and
a fun first smart-home build to do together with kids.

**Parts:**

- An ESP8266 board — "ESP-12F" / "D1 Mini" (a few euros, widely
  available — e.g. [Reichelt (DE)](https://www.reichelt.de/d1-mini-kompatibles-esp8266-board-v2-0-d1-mini-p253978.html);
  see [docs/bastler-edition-teileliste.md](docs/bastler-edition-teileliste.md)
  for more sources, including the US)
- A TCRT5000 infrared reflective sensor module — optical, so no
  magnets to glue to the wheel and nothing a hamster can chew through
- Jumper wires and a small breadboard (or a 3D-printed mount, see
  `cad/`)

<figure>
  <img src="docs/wiring-d1-mini-tcrt5000.svg" alt="Verkabelung D1 Mini mit TCRT5000: 3V3 zu VCC, GND zu GND, D2/GPIO4 zu D0/OUT. Der TCRT5000 erkennt optisch eine Markierung auf dem Laufrad, einmal pro Umdrehung." width="680">
  <figcaption>D1 Mini ↔ TCRT5000 wiring — 3 wires, no soldering.</figcaption>
</figure>

**Steps:**

1. Wire the TCRT5000 module to the ESP8266: signal/`D0` → `D2`
   (GPIO4), plus `VCC` → `3V3` and `GND` → `GND` (see diagram above).
2. Open `esphome/hamster-wheel-sensor.yaml` in ESPHome and flash it to
   your board — this config is written and tuned specifically for
   this ESP8266 + TCRT5000 setup, so there's nothing else to configure.
3. In your ESPHome `secrets.yaml` file, add these four entries:
   `wifi_ssid`, `wifi_password`, `esphome_web_d027a9__encryption_key`,
   `esphome_web_d018de__ota_password`.
4. Mount the sensor next to the wheel so it "sees" one mark (e.g. a
   strip of tape or a printed marker) once per full turn.
5. Once it's flashed, Home Assistant should find it automatically
   through the ESPHome integration.
6. Install [ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration)
   and point it at this sensor's rotation-count entity.

Outgrown the breadboard, or want to skip soldering entirely? See
[ROADMAP.md](ROADMAP.md) for the planned Plug-and-Play PCB and Deluxe
editions.

## Support this project

Hamster Fitness is free and always will be. If it's useful to you and you
want to say thanks, you can [buy me a coffee on Ko-fi](https://ko-fi.com/R8O124JOD1).
Not required — just appreciated.
